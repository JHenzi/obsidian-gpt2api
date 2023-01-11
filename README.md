## _Project Status: **On Hold/Research (2023-01-11)**_

## GPT-2 Autocompletion for Obsidian.md via API

Welcome and first, apologies, when reading this you may be looking for a completed and running plugin, however this is currently a work in progress.

> **Intention**
>
> *Having an endpoint where we can call GPT-2 [^GPTAPISource] we are looking to get the predictions or suggestions from GPT-2's language model to suggest our next set of words in the Obsidian note. What we lack is the UI to match the API end-point, while other plugins provide "complements" or "autocompletion" they lack the back-end processing available with GPT-2.*

## Project Log

*This will be split into it's own file later, tracking the build status as we go at a high-level as there may be (i.e. will be) times when life is more important than messing around with code we intend to learn from messing with.*

- 2022-12-20
  - Setup root of project, GitHub mirror
  - Had a short chat session with ChatGPT to get *advice* on where to start (result: learn the Obsidian API, which seems fair)
- 2022-12-21
  - Revisiting plan, updating related files outside of project folder (i.e. notes, backups)
  - Installed newer plugins/updated plugins that offer similar types of functionality to dive into their methods. Key updates/new plugins worth mentioning:
    - **Obsidian Ava**: Promises to be your all-in-one AI assistant for Obsidian. Taps into GPT-3 from OpenAI directly (all models). Has other features including a FastAPI enabled 'semantic search' server (which didn't work for me due to a TensorFlow error despite installing requirements).
    - **Completr**: Newer 'autocomplete' solution as the original plugin is no longer maintained and its author points to Completr
  - [Revisiting Obsidian API documentation](https://github.com/obsidianmd/obsidian-api)
    - *Competing priorities for the day mean this may remain incomplete, meant as a refresher and not a true deep-dive*
    - *Needed: Early decision on the best mechanism(s) to perform the 'type ahead' suggestions, hotkey enabled, based on a paused cursor, command pallet, etc.*
- 2022-12-27
  - Took the holidays "off" not working directly on this project. Instead I spent some of the time with ChatGPT to round out calling the Hugging Face model BLOOM for text generation.
  - As of 20220-12-26 we have a working BLOOM endpoint as well, also leveraging FastAPI (/tasks endpoint).
  - *Note, the BLOOM enabled endpoint is not designed, necessarily, for this body of work and is only tangentially related!*
  - *Usage of BLOOM is more aligned to our 'Task Enhancer' project that hasn't yet been posted here on GitHub*
  - **No work on this project will take place on 2022-12-27, focus is needed elsewhere**
- 2023-01-11
  - Check-In: I've **not** spent any more time on the UI portion of the project, in fact not spending as much time Obsidian.md as typical.
  - Released, instead **The Henzi NLP Playground**, which is currently hosted @ [PiVPN.XYZ](https://pivpn.xyz)
    - Eventually the NLP Playground's backend, running FastAPI, the BLOOM language model will be pushed to Github
    - The React-driven front end will also be published when the source includes some missed features (Routing and/or Hash Routing to start)
  - Having seen results from GPT-2, BLOOM and others I'm not terribly convinced they are powerful tools for note taking.
    - Being said, one thought might be to enable an API, open the code (common backend for the app mentioned above) but have this work with an existing auto-complete tool for Obsidian, one which simply needs another source of completion suggestions. As I test those solutions in the application I am leaning towards one but will save mentioning the contender as I have negative tests to perform.
 

[^GPTAPISource]: We have enabled, with the help of ChatGPT, the endpoint by writing a Python app to suggest text based on the GPT-2 model from OpenAI. The exercise was to both create a self-hosted endpoint but to test out the "programming" capabilities of ChatGPT. It was a success. We are running GPT-2 via the Hugging Face Transformers library and then making results available via a REST API by using FastAPI to expose the method. This has been tested in both a Telegram 'chatbot' and by leveraging the API in Node Red to create a UI to enter text and see predictions in near-real-time. This project looks to simply call the API, provide suggestions for 'tab completion' (or another hotkey) in Obsidian.md depending on whatever craziness GPT-2 comes up with! That code is pretty elementary and likewise not super clean as it was primarily written by a bot, though with interest I would publish to GitHub. Otherwise both that and this are mainly personal "wouldn't it be cool if..." projects and potentially not super useful. GPT-3, a better model, is accessible today via an API call and another plugin in Obsidian if a user want's valuable results.
