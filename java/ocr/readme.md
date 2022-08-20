# OCR in Java

## Setup
```bash
brew install tesseract
```
for support of other languages
```bash
brew install tesseract-lang
```

## Using custom tessdata

Download [trained tessdata](https://github.com/tesseract-ocr/tessdata) for
several languages and put them under folder, it could be located under resource
folder or any other path outside of the application
If folder is located under resource folder, use the next code
```java
var tesseract = new Tesseract();
var tessdata = LoadLibs.extractTessResources("tessdata");
tesseract.setDatapath(tessdata.getAbsolutePath());
```
or if you know the absolute path, just write it in the `setDataPath`
```java
var tesseract = new Tesseract();
tesseract.setDataPath("/opt/ocr/tessdata");
```
Under the folder you will have files with the next names:
* deu.traineddata
* eng.traineddata
* osd.traineddata

the first part of the name is important, we will use for setting languages

## Set language

The image that you will OCRing could contain one or multiple languages, in that
case you will need to define which language is expected, by default `eng` is
enabled

```java
var tesseract = new Tesseract();
tesseract.setDataPath("/opt/ocr/tessdata");
// It means we expect that Deutschland or English languages will appear in the image
tesseract.setLanguage("deu+eng");
```

## Get OCR result

The library `tess4j` supports multiple options to work with input content, it
could be `File` or `BufferedImage` or `ByteBuffer`, also you could define do you
want to extract the text from the whole file, or a concrete Bounding Box

```java
var tesseract = new Tesseract();
tesseract.setDataPath("/opt/ocr/tessdata");
tesseract.setLanguage("deu+eng");
var inputImage = new File("/opt/exmaples/images/multi-language.png")
String fullPageResult = tesseract.doOcr(inputImage);
String rectangleResult = tesseract.doOcr(inputImage, new Rectangle(100, 100, 100, 100));
```

## Troubleshooting

### Unable to load library 'tesseract'
This one was resolved by providing the path to jna libraries system property

```java
String libPath = "/usr/local/lib";
File libTess = new File(libPath, "libtesseract.dylib");
if (libTess.exists()) {
  String jnaLibPath = System.getProperty("jna.library.path");
  if (jnaLibPath == null) {
    System.setProperty("jna.library.path", libPath);
  } else {
    System.setProperty("jna.library.path", libPath + File.pathSeparator + jnaLibPath);
  }
} else {
  throw new RuntimException(String.format("OCR: validate: Tesseract library not in /usr/local/lib"));
}
```

## Links
* [Baeldung article](https://www.baeldung.com/java-ocr-tesseract)
* [Tesseract User Manual](https://tesseract-ocr.github.io/tessdoc/Home.html)
* [Best tessdata](https://github.com/tesseract-ocr/tessdata_best)
* [Fast tessdata](https://github.com/tesseract-ocr/tessdata_fast)
* [Combined (Best + Fast) tessdata](https://github.com/tesseract-ocr/tessdata)
* [Hint to resolve the issue with not loaded libraries](https://github.com/RaiMan/SikuliX1/commit/49f1bf3e5330365c97085b9533050bd538119c62)
* [How to provide more than one language to the tesseract](https://stackoverflow.com/questions/24379781/how-can-i-run-tesseract-with-multiple-languages-one-time)
* [How to OCR with Tesseract, OpenCV and Python](https://nanonets.com/blog/ocr-with-tesseract/)
* [Tesseract Page Segmentation Modes (PSMs) Explained: How to Improve Your OCR Accuracy]
(https://pyimagesearch.com/2021/11/15/tesseract-page-segmentation-modes-psms-explained-how-to-improve-your-ocr-accuracy/)
* [All OCR options](https://muthu.co/all-tesseract-ocr-options/)
