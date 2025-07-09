# textify
BCA project TEXTIFY 


Here's a detailed README.md file for your TEXTIFY project:

# TEXTIFY: Image/PDF to Text Conversion with OCR

TEXTIFY is a web application built with Flask that allows users to upload images or PDF files and extract text from them using Optical Character Recognition (OCR) technology. The application utilizes the TrOCR (Transformer-based Optical Character Recognition) model from the Hugging Face Transformers library for accurate and efficient text extraction.

## Features

- User authentication (sign-up and login)
- File upload (images and PDFs)
- OCR text extraction from uploaded files
- Lazy loading of images for better performance
- Copy extracted text to clipboard
- Download extracted text as a text file
- Contact form for user inquiries and feedback

## Technologies Used

- Python
- Flask (Web Framework)
- Hugging Face Transformers (TrOCR model)
- OpenCV (Image Processing)
- PDF2Image (PDF to Image Conversion)
- HTML/CSS/JavaScript (Front-end)
- Bootstrap (CSS Framework)

## Prerequisites

Before running the application, ensure that you have the following software installed on your system:

- Python (version 3.6 or higher)
- pip (Python package installer)

## Installation

1. Clone the repository:

```
git clone https://github.com/your-username/TEXTIFY.git
```

2. Navigate to the project directory:

```
cd TEXTIFY
```

3. Create a virtual environment (optional but recommended):

```
python -m venv env
```

4. Activate the virtual environment:

   - On Windows:
   ```
   env\Scripts\activate
   ```

   - On macOS/Linux:
   ```
   source env/bin/activate
   ```

5. Install the required Python packages:

```
pip install -r requirements.txt
```

## Usage

1. Run the Flask application:

```
python app.py
```

2. Open your web browser and go to `http://localhost:5000`.

3. Sign up for a new account or log in if you already have one.

4. On the upload page, click the "Choose an Image or PDF" button to select a file from your local machine.

5. After selecting the file, click the "Upload" button.

6. Wait for the OCR process to complete. The extracted text will be displayed on the page.

7. You can copy the extracted text to your clipboard by clicking the "Copy Text" button or download it as a text file by clicking the "Download Text" button.

8. To contact the developers or provide feedback, navigate to the "Contact Us" page and fill out the contact form.

## Code Flow

1. The `app.py` file is the main entry point of the Flask application. It handles various routes and functionalities, such as user authentication, file upload, and OCR text extraction.

2. When a user uploads a file, the `convert` route in `app.py` is triggered. This route calls the `ocr_core` function from the `ocr_pro.py` file, which performs the actual OCR text extraction.

3. The `ocr_core` function checks the file type (image or PDF) and calls the appropriate processing function (`process_image` or `process_pdf`) from `ocr_pro.py`.

4. For image files, the `process_image` function preprocesses the image using the TrOCR processor and performs text recognition using the TrOCR model.

5. For PDF files, the `process_pdf` function first converts the PDF to a series of images using the `pdf2image` library. Then, it iterates over each page image, extracts the text using the TrOCR model, and concatenates the results.

6. The extracted text is returned to the `convert` route in `app.py` and rendered on the `upload.html` page.

7. The `upload.html` template includes JavaScript code (`script.js`) that handles the copy and download functionality for the extracted text.

8. The `lazyload.js` file implements lazy loading for images, ensuring better performance by loading images only when they are visible on the page.

9. The `login.html`, `signup.html`, and `about.html` templates handle user authentication and the contact form, respectively.

10. The `main.js` file handles form validation and submission for the contact form.

## References

- [Flask Documentation](https://flask.palletsprojects.com/en/2.2.x/)
- [Hugging Face Transformers Documentation](https://huggingface.co/docs/transformers/index)
- [OpenCV Documentation](https://opencv.org/docs/)
- [PDF2Image Documentation](https://pdf2image.readthedocs.io/en/latest/)

## License

This project is licensed under the [MIT License](LICENSE).

## Acknowledgments

- The TrOCR model was developed by Microsoft and is available through the Hugging Face Transformers library.
- The lazy loading implementation is based on the [Lazy Load XT](https://github.com/ressio/lazy-load-xt) library.
- The contact form template is adapted from [Colorlib](https://colorlib.com/wp/template/contact-form-06/).

## Contributing

Contributions are welcome! If you find any bugs or have suggestions for improvement, please open an issue or submit a pull request.

## Scopes and Upgradability

### Scopes

- **Document Digitization**: TEXTIFY can be used for digitizing and extracting text from various types of documents, such as books, reports, contracts, and handwritten notes. This can be particularly useful for archiving and preserving physical documents in a digital format.

- **Accessibility**: The ability to convert images and PDFs into text can greatly improve accessibility for individuals with visual impairments or learning disabilities, as the extracted text can be read aloud by screen readers or text-to-speech software.

- **Data Entry and Processing**: TEXTIFY can streamline data entry processes by automatically extracting text from scanned documents or images, reducing the need for manual data entry and minimizing errors.

- **Research and Analysis**: Researchers and analysts can use TEXTIFY to extract text from various sources, such as historical documents, scientific papers, or image-based data, facilitating further analysis and interpretation.

### Upgradability

- **Handwriting Recognition**: Incorporating advanced handwriting recognition capabilities could significantly expand the application's usefulness for digitizing handwritten documents, such as notes, letters, or forms.

- **Language Support**: Currently, TEXTIFY relies on the TrOCR model, which primarily supports English text recognition. Integrating additional language models could enable text extraction in multiple languages, catering to a wider user base.

- **Document Layout Analysis**: Implementing document layout analysis algorithms could improve the organization and formatting of the extracted text, making it more readable and preserving the original document structure.

- **Batch Processing**: Adding support for batch processing of multiple files simultaneously could increase efficiency and productivity for users with large volumes of documents to process.

- **Cloud Integration**: Integrating TEXTIFY with cloud storage services (e.g., Google Drive, Dropbox) could allow users to upload files directly from their cloud storage accounts, streamlining the upload process and enabling remote access.

## Use Cases

TEXTIFY can be valuable in various scenarios, including:

- **Digital Archiving**: Libraries, museums, and historical societies can use TEXTIFY to digitize and preserve physical documents, making them more accessible and searchable.

- **Legal and Financial Document Processing**: Law firms and financial institutions can leverage TEXTIFY to extract text from contracts, agreements, and other legal or financial documents, facilitating document management and analysis.

- **Academic Research**: Researchers and scholars can use TEXTIFY to extract text from various sources, such as historical documents, scientific papers, or image-based data, enabling further analysis and interpretation.

- **Accessibility Solutions**: TEXTIFY can be integrated into accessibility tools and assistive technologies to help individuals with visual impairments or learning disabilities by converting images and PDFs into readable text.

- **Data Entry and Processing**: Organizations can streamline their data entry processes by using TEXTIFY to automatically extract text from scanned documents or images, reducing the need for manual data entry and minimizing errors.

## Advantages

- **Accurate Text Extraction**: The TrOCR model used in TEXTIFY provides accurate and reliable text extraction from images and PDFs, ensuring high-quality results.

- **User-Friendly Interface**: The web-based interface of TEXTIFY makes it accessible and easy to use for a wide range of users, without the need for complex software installations or configurations.

- **Versatility**: TEXTIFY supports various file formats, including images (PNG, JPG, JPEG, GIF, TIFF) and PDFs, catering to different document types and sources.

- **Lazy Loading**: The implementation of lazy loading ensures better performance by loading images only when they are visible on the page, improving the overall user experience.

- **Copy and Download Options**: Users can easily copy the extracted text to their clipboard or download it as a text file, enabling further processing or integration with other applications.

- **Contact Form**: The integrated contact form allows users to provide feedback, report issues, or request additional features, facilitating continuous improvement and support.

## Disadvantages and Limitations

- **Language Limitations**: Currently, TEXTIFY primarily supports English text recognition due to the limitations of the TrOCR model. Support for additional languages may require integrating additional language models.

- **Handwriting Recognition**: While TEXTIFY can extract text from printed documents and images, it may struggle with handwritten text recognition, as the TrOCR model is primarily designed for printed text.

- **Document Layout Preservation**: The extracted text may not preserve the original document layout and formatting, making it less suitable for applications that require precise layout preservation.

- **File Size Limitations**: Processing large files or high-resolution images may be resource-intensive and slower, potentially affecting the performance and responsiveness of the application.

- **Cloud Integration**: The current version of TEXTIFY lacks integration with cloud storage services, which could limit its accessibility for users who prefer to work with cloud-based files.

## Future Upgradability

- **Handwriting Recognition**: Incorporating advanced handwriting recognition capabilities could significantly expand the application's usefulness for digitizing handwritten documents, such as notes, letters, or forms.

- **Language Support**: Integrating additional language models could enable text extraction in multiple languages, catering to a wider user base.

- **Document Layout Analysis**: Implementing document layout analysis algorithms could improve the organization and formatting of the extracted text, making it more readable and preserving the original document structure.

- **Batch Processing**: Adding support for batch processing of multiple files simultaneously could increase efficiency and productivity for users with large volumes of documents to process.

- **Cloud Integration**: Integrating TEXTIFY with cloud storage services (e.g., Google Drive, Dropbox) could allow users to upload files directly from their cloud storage accounts, streamlining the upload process and enabling remote access.

## System Requirements

### Hardware Requirements
- Processor: Intel Core i5 or equivalent
- RAM: 8 GB or higher
- Storage: Sufficient storage space for the application and processed files

### Software Requirements
- Operating System: Windows, macOS, or Linux
- Python (version 3.6 or higher)
- Web Browser (latest version of Google Chrome, Firefox, or Safari)

## Flowchart

Here's a high-level flowchart illustrating the flow of the TEXTIFY application:

```
┌────────────────────┐
│      Start         │
└───────────┬────────┘
            │
            ∨
┌────────────────────┐
│  User Authentication
│  (Login or Sign up)│
└───────────┬────────┘
            │
            ∨
┌────────────────────┐
│    File Upload     │
└───────────┬────────┘
            │
            ∨
┌────────────────────┐
│   OCR Processing   │
└───────────┬────────┘
            │
            ∨
┌────────────────────┐
│  Extract Text      │
└───────────┬────────┘
            │
            ∨
┌────────────────────┐
│   Display Result   │
└───────────┬────────┘
            │
            ∨
┌────────────────────┐
│Copy/Download/Contact│
└───────────┬────────┘
            │
            ∨
┌────────────────────┐
│      End           │
└────────────────────┘
```

## ER Diagram

The TEXTIFY application does not utilize a relational database in its current implementation. Therefore, an ER (Entity-Relationship) diagram is not applicable in this case.

## Algorithms

### OCR Text Extraction

The OCR text extraction process in TEXTIFY utilizes the TrOCR (Transformer-based Optical Character Recognition) model from the Hugging Face Transformers library. The algorithm follows these steps:

1. **Preprocess Image**:
   - Convert the input image to RGB format.
   - Convert the PIL image to a NumPy array.
   - Preprocess the image using the TrOCR processor to obtain pixel values suitable for the model.

2. **Perform Text Recognition**:
   - Pass the preprocessed pixel values to the TrOCR model for text recognition.
   - The model generates a sequence of IDs representing the recognized text.

3. **Decode Text**:
   - Use the TrOCR processor to decode the generated IDs into human-readable text.
   - Remove any special tokens or unwanted characters from the decoded text.

4. **Return Extracted Text**:
   - Return the extracted text as a string.

For PDF files, the process involves an additional step of converting the PDF to a series of images using the `pdf2image` library. The OCR text extraction algorithm is then applied to each page image, and the results are concatenated to form the final extracted text.
