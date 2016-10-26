#Computer Vision API Version 1.0

Computer Vision cloud-based API provides developers with access to advanced algorithms for processing images and returning information. By uploading an image or specifying an image URL, Microsoft Computer Vision algorithms can analyze visual content in different ways based on inputs and user choices. With the Computer Vision API users can analyze images to:
- Tag images based on content.
- Categorize images.
- Identify the type and quality of images. 
- Recognize domain specific content (celebrities model).
- Generate descriptions of the content. 
- Use optical character recognition to identify text found in images.
- Distinguish color schemes.
- Flag adult content.
- Detect human faces and return their coordinates in the image.   
- Crop photos to be used as thumbnails. 

##Tagging Images
Computer Vision API returns tags based on more than 2000 recognizable objects, living beings, scenery, and actions. In cases where tags may be ambiguous or not common knowledge, the API response provides “hints” to clarify the meaning of the tag in context of a known setting. Tags are not organized as a taxonomy and no inheritance hierarchies exist. A collection of content tags forms the foundation for an image “description” displayed as human readable language formatted in complete sentences. Note, that at this point English is the only supported language for image description.

Computer Vision API will also support specialized (or domain-specific) information. Specialized information can be implemented as a stand-alone method or in combination with the "analyze" method. Specialized information is a way to break down the 86-category taxonomy into domain-specific models. Right now, we only support celebrity-recognition as a domain-specific model, but more will be added soon! 

##Categorizing images
In addition to tagging and descriptions, Computer Vision API returns the taxonomy-based categories defined in previous versions. These categories are organized as a taxonomy with parent/child hereditary hierarchies. All categories are in English.They can be used alone or in combination with our new models.

##Identifying Image Types
There are several ways to categorize images. Computer Vision API can set a boolean flag to indicate whether an image is black and white or color and use the same method to indicate whether an image is a line drawing or not. It can also indicate whether an image is clipart or not and indicate its quality as such on a scale of 0-3. 

##Recognizing Domain-Specific Content: Celebrities Model
A new domain-specific model has been added to Computer Vision API, in this case a model that recognizes celebrities in your images. It can be implemented as a stand-alone method or in combination with the top-level image categorization. 

##Generating Descriptions
Computer Vision API’s algorithms analyze the content found in an image, which in turn forms the foundation for a “description” displayed as human readable language in complete sentences. The description summarizes what is found in the image. More than one description will be generated for each image ordered by their confidence score as seen in below illustration.

##Perceiving Color Schemes
The Computer Vision algorithm extracts colors from an image. The colors are analyzed in three different contexts, foreground, background, and whole, and colors are grouped into twelve 12 dominant accent colors (black, blue, brown, gray, green, orange, pink, purple, red, teal, white, and yellow). Depending on the colors in an image, simple black and white or accent colors may be returned in hexadecimal color codes.

##Flagging Adult Content
Among the various visual categories is the adult and racy group, which enables detection of pornographic materials and restricts the display of images containing sexual content. The filter for adult and racy content detection can be set on a sliding scale to accommodate the user’s preference.

##Detecting faces
Computer Vision API detects human faces within a picture and generates face coordinates, draws the bounding box around the face, indicates gender and age. These visual features are a subset of metadata generated for Face API. For more extensive metadata generated for faces, such as facial identification, pose detection, and more, use the Face API.

##TBD
- Supported input methods: Raw image binary in the form of an application/octet stream or image URL.
- Supported image formats: JPEG, PNG, GIF, BMP.
- Image file size: Less than 4MB.
- Image dimension: Greater than 50 x 50 pixels.

``` 
Returned Json 
 “description”: 
{
    "captions": 
[
{
"type": "phrase",
“text”: “a black and white photo of a large city”,
          “confidence”: 0.607638706850331
}
]
"captions": 
[
{
"type": "phrase",
“text”: “a photo of a large city”,
          “confidence”: 0.577256764264197
    }
]
"captions": 
[
{
"type": "phrase",
“text”: “a black and white photo of a city”,
          “confidence”: 0.538493271791207
}
]
“description”: 
[
"tags": 
{
      "outdoor", "city", "building", "photo", "large", 
}
]
}
```



##Generate a thumbnail

A thumbnail is a small representation of a full-size image. Varied devices such as phones, tablets, and PCs create a need for different user experience (UX) layouts and thumbnail sizes. Using smart cropping, this Computer Vision API feature helps solve the problem. The algorithm analyzes the objects within the image, then crops it to fit “the region of interest” (ROI). The generated thumbnail can be presented in a different aspect ratio than that of the original image to accommodate a user’s needs. 

##OCR

Optical Character Recognition (OCR) is a technology that detects text content in an image and subsequently extracts the identified text into 