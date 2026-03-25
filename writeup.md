## How did the LLM know to call your new tool?

The tool is saved to stock_tools with a name and a description, the model for example sees that compare_stock is meant to compare two stocks side by side.
So when a user asks to compare two stocks, the llm does a semantic search and gets the compare stock tool.

## What happens if the tool schema description is unclear?

If the description is unclear then the llm might map the user's requests to a tool that he did not ask for, or just skip the tool directly.

## How does the agent decide between compare_stocks and get_stock_price?

it maps the user's requests to the description of the tools. the model is able to distinquish between comparing stocks and get a stock's price due to both tool's description.

## How would you add validation for parameter values?

Normalizing values and making sure they are not empty. Also some errors could be recuced based on developer's experience and intention, for example
the developer may decide not to allow the user to compare the same stock with itself or input empty values, or input a stock ticker that is not in a premade list.

## What if the user asks to compare 3 stocks instead of 2?

The model would struggle as the tools only have two parameters, we would have to change the whole tool and how it processes the parameters.
