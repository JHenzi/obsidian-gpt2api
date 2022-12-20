# GPT-2 Autocompletion for Obsidian.md via API

Welcome and first, apologies, when reading this you may be looking for a completed and running plugin, however this is currently a work in progress.

> **Intention**
>
> *Having an endpoint where we can call GPT-2 [^GPTAPISource] we are looking to get the predictions or suggestions from GPT-2's language model to suggest our next set of words in the Obsidian note. What we lack is the UI to match the API end-point, while other plugins provide "complements" or "autocompletion" they lack the back-end processing available with GPT-2.*

[^GPTAPISource]: We have enabled, with the help of ChatGPT, the endpoint by writing a Python app to suggest text based on the GPT-2 model from OpenAI. The exercise was to both create a self-hosted endpoint but to test out the "programming" capabilites of ChatGPT. It was a success. We are running GPT-2 via the Hugging Face Transformers library and then making results available via a REST API by using FastAPI to expose the method. This has been tested in both a Telegram 'chatbot' and by leveraging the API in Node Red to create a UI to enter text and see predictions in near-real-time. This project looks to simply call the API, provide suggestions for 'tab completion' (or another hotkey) in Obsidian.md depending on whatever craziness GPT-2 comes up with! That code is pretty elementary and likewise not super clean as it was primarily written by a bot, though with interest I would publish to GitHub. Otherwise both that and this are mainly personal "wouldn't it be cool if..." projects and potentially not super useful. GPT-3, a better model, is accessible today via an API call and another plugin in Obsidian if a user want's valuable results.
