# AI Image Classifier 🖼️

A simple and interactive web application built with Streamlit that uses a pre-trained deep learning model (MobileNetV2) to classify the content of uploaded images.

<img width="1920" height="1080" alt="Screenshot 2025-08-27 101301" src="https://github.com/user-attachments/assets/97df7b91-6e26-4616-9aae-c284ed75e5ce" />


---

## Features

-   **Interactive Web Interface**: A user-friendly UI created with Streamlit.
-   **Image Upload**: Supports uploading images in `JPG` and `PNG` formats.
-   **Powerful AI Model**: Utilizes the **MobileNetV2** model, pre-trained on the ImageNet dataset, for fast and accurate classifications.
-   **Top Predictions**: Displays the top 3 most likely classifications for an image along with their confidence scores.
-   **Efficient Caching**: The model is cached on its first run to ensure fast performance for subsequent classifications.

---

## Technologies Used

-   **Streamlit**: For building the web application interface.
-   **TensorFlow & Keras**: For loading and using the MobileNetV2 model.
-   **OpenCV**: For image resizing and processing.
-   **Pillow (PIL)**: For handling image files.
-   **NumPy**: For numerical operations and image manipulation.

---

## Setup and Installation

Follow these steps to set up and run the project on your local machine.

### Prerequisites

-   Python 3.8 or newer
-   [uv](https://github.com/astral-sh/uv) (Python package installer)

### 1. Clone the Repository

First, clone this repository to your local machine (or simply download the files).

```bash
git clone <https://github.com/ParthBharadia/AI_project>
cd <AI_project>
```

### 2. Create a Virtual Environment with `uv`

It's highly recommended to create a virtual environment to manage project dependencies. `uv` makes this fast and simple.

```bash
# Create the virtual environment using uv
uv venv

# Activate it
# On Windows
venv\Scripts\activate

# On macOS/Linux
source v-env/bin/activate
```

### 3. Install Dependencies with `uv`

Create a file named `requirements.txt` and add the following lines to it:

```
streamlit
tensorflow
opencv-python-headless
numpy
Pillow
```

Now, install all the necessary libraries using `uv`. It's significantly faster than traditional `pip`.

```bash
uv pip install -r requirements.txt
```

---

## How to Run the Application

Once the setup is complete, you can run the Streamlit application with a single command. Make sure you are in the project's root directory where your Python script is located.

```bash
uv run streamlit run your_script_name.py
```
*(Replace `your_script_name.py` with the actual name of your Python file.)*

The application will open automatically in your web browser.

---

## How It Works

1.  **Load Model**: The application loads the pre-trained `MobileNetV2` model from `tensorflow.keras.applications`. The `@st.cache_resource` decorator ensures the model is loaded only once.
2.  **Image Upload**: The user uploads an image through the Streamlit file uploader.
3.  **Preprocessing**: The uploaded image is resized to 224x224 pixels and preprocessed to match the input format required by MobileNetV2.
4.  **Prediction**: The processed image is passed to the model, which returns a set of predictions.
5.  **Display Results**: The top 3 predictions are decoded into human-readable labels and displayed on the screen with their corresponding confidence scores formatted as percentages.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for more details.

