Story Teller
Story Teller is a Streamlit application that generates a story based on an input image. It utilizes the Hugging Face Transformers library and the Salesforce BLIP Image Captioning model.

Table of Contents
Installation
Usage
API Token
Models
Running the Application
Contributing
License
Installation
To install the necessary dependencies, run the following command:

shell
Copy code
pip install -r requirements.txt
Make sure you have the required dependencies specified in the requirements.txt file.

Usage
To use the application, follow the steps below:

Run the Streamlit application by executing the following command:

shell
Copy code
streamlit run app.py
Access the application through the provided URL in the console.

The application interface will appear with the title "Story Teller" and an instruction to "Upload an image and get a story".

Click on the "Upload your file here..." button to select an image file (supported formats: PNG, JPEG, JPG).

Once the image is uploaded, it will be displayed on the page.

The application will process the uploaded image using the Salesforce BLIP Image Captioning model and generate a textual description of the image.

The generated text will then be passed to the Hugging Face API to generate a story based on the text.

The application will display the generated story on the page.

If any errors occur during the process, an error message will be shown on the page, and you can try again.

API Token
The application requires an API token from Hugging Face to access the story generation model. To obtain an API token, follow these steps:

Sign up or log in to your Hugging Face account at https://huggingface.co/.

Once logged in, go to your account settings and navigate to the "API token" section.

Generate a new API token, copy it, and replace the "your api key" placeholder in the Models class of text_model.py with your actual API token.

Models
The Models class in text_model.py encapsulates the functionality of the application. It contains the following methods:

__init__(): Initializes the class and sets the API token and model ID.

img2text(url): Takes an image URL as input and uses the Salesforce BLIP Image Captioning model to convert the image into text. It returns the generated text.

story(payload): Takes a payload as input, which contains the generated text, and sends a request to the Hugging Face API to generate a story based on the text. It returns the generated story.

chain(payload, num=0): This method acts as a recursive function that generates a chain of stories. It takes a payload as input, which initially contains the generated text. It recursively calls the story() method and updates the payload until the desired number of stories (50 in this case) is generated. The progress bar is also updated accordingly.

Running the Application
To run the application, execute the following command:

shell
Copy code
python main.py
Make sure you have the required dependencies installed, as mentioned in the installation section.

Contributing
Contributions to the Story Teller application are welcome! If you find any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.
