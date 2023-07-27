# 5wqa

## Data 
Data can be obtained form this link: 

## Paraphrasing Text with OpenAI GPT-3

This Jupyter notebook is used for generating paraphrases of text using OpenAI's GPT-3 model, specifically the 'gpt-3.5-turbo' version of the model. 

## Dependencies

The main dependencies for this notebook are:

- `numpy`
- `pandas`
- `openai`
- `tqdm`
- `time`
- `tenacity`

## Data

The input data is a JSON file. The JSON file contains claims with evidence.

## Code Overview

The code follows these steps:

1. Import the necessary libraries.
2. Load the JSON data into a pandas DataFrame.
3. Define the `get_answers()` function, which sends a text prompt to the OpenAI API and returns the generated response. This function is decorated with a retry mechanism to handle potential API errors.
4. Define the prompt for the OpenAI API, instructing it to generate 5 different paraphrases of a given text and format the output as a list.
5. Process the claims in the DataFrame, generate paraphrases using the `get_answers()` function, handle potential rate limit errors from the OpenAI API, and periodically save the results to a CSV file.

## Running the Code

To run this notebook, you need to set your OpenAI API key in the appropriate code cell. The API key is used to authenticate your requests to the OpenAI API.

You also need to adjust the range of DataFrame rows to process in the main loop according to your requirements.

The code saves the paraphrased text to a CSV file periodically and at the end of processing. The filename for the CSV file is `paraphrase_text.csv`.

Set the Index in 2nd last cell of the notebook.
## Notes

Please ensure that you have enough quota to make the necessary API calls to the OpenAI API. If you exceed the rate limit, the code will try to handle this by waiting for a certain amount of time before retrying.
