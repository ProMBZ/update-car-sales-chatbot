# Car Sales Chatbot

This Streamlit application implements a car sales chatbot powered by LangChain and Google's Gemini 2.0 Flash LLM. It interacts with users, provides information about used cars, compares prices, and collects leads.

## Features

-   **Car Information:** Retrieves details about available used cars, including mileage, interior, and benefits, with image retrieval.
-   **Price Comparison:** Compares car prices with online listings using Tavily Search API, applying a discount factor for competitive pricing.
-   **Lead Collection:** Collects user contact information (name, email, WhatsApp) via an inline form.
-   **Conversation Memory:** Maintains conversation history using LangChain's `ConversationBufferMemory`.
-   **Dynamic UI:** Uses Streamlit for a responsive and interactive user interface with custom CSS and animations.
-   **Fuzzy Matching:** Implements fuzzy matching with `difflib` to handle slight variations in car model names.
-   **Tavily Search API Integration:** Retrieves search results and images using the Tavily Search API.
-   **Environment Variable Handling:** Uses `.env` files to manage API keys.

## Prerequisites

-   Python 3.7+
-   Streamlit
-   LangChain
-   `langchain-google-genai`
-   Tavily
-   python-dotenv
-   `difflib` (standard library)
-   `re` (standard library)
-   Google Gemini API key
-   Tavily API key

## Installation

1.  Clone the repository:

    ```bash
    git clone <repository_url>
    cd <repository_directory>
    ```

2.  Create a virtual environment (recommended):

    ```bash
    python -m venv venv
    source venv/bin/activate  # On macOS/Linux
    venv\Scripts\activate  # On Windows
    ```

3.  Install the required packages:

    ```bash
    pip install streamlit langchain langchain-google-genai tavily python-dotenv
    ```

4.  Create a `.env` file in the project root and add your API keys:

    ```
    GOOGLE_API_KEY=your_google_api_key
    TAVILY_API_KEY=your_tavily_api_key
    ```

## Usage

1.  Run the Streamlit application:

    ```bash
    streamlit run app.py
    ```

2.  Open the application in your browser (usually `http://localhost:8501`).

3.  Interact with the chatbot by typing your questions or requests.

## Code Structure

-   `app.py`: Contains the main Streamlit application code, including:
    -   API key configuration.
    -   LLM and Tavily client initialization.
    -   Used car stock data.
    -   Tool definitions (price comparison, car details, etc.).
    -   LangChain agent setup.
    -   Streamlit UI elements and logic.
    -   Lead collection form.
-   `leads.csv`: Stores collected lead information.
-   `.env`: Stores API keys (not committed to version control).

## Customization

-   **Used Car Stock:** Modify the `used_car_stock` dictionary in `app.py` to add or remove cars.
-   **API Keys:** Replace the placeholder API keys in `.env` with your own.
-   **Styling:** Customize the CSS in the `st.markdown` section to change the appearance of the application.
-   **Tools:** Add or modify LangChain tools to extend the chatbot's functionality.
-   **Prompt Engineering:** Adjust the prompts and instructions given to the LLM to improve its responses.
-   **Discount Factor:** Change the `discount_factor` variable within the `compare_prices` function to adjust the price discount.
-   **Dealership Benefits:** Update the `additional_info` variable inside of the `why_buy_from_us` function to reflect the dealership's benefits.

## Notes

-   Ensure your API keys are kept secure and not exposed in your code or version control.
-   The accuracy of price comparisons depends on the availability and accuracy of online data retrieved by Tavily Search.
-   This application is intended for demonstration purposes and may require further development for production use.
-   The dummy car stock data can be replaced with a real database or API connection.
-   Error handling can be improved to provide more robust behavior.
