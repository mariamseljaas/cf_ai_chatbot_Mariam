# PROMPTS.md

This file lists a few of the AI prompts I used while developing the project.  
These were mainly for help understanding specific APIs or clarifying error messages.

---


### Prompt 1
“I’m getting an error with OPENAI_API_KEY not being configured when deploying. What am I missing?”

Assistant Response:
"Usually that means Wrangler isn't picking it up. Make sure .dev.vars is in the root folder (same level as wrangler.jsonc), and restart the dev server. Also check for typos like OPENAI_API_KEY vs OPENAI-API-KEY."

### Prompt 2
“I added a to do list tool to my agent using storage.put and storage.get. Here’s the execute function I wrote (screenshot). Is the way I am updating the array makes sense, or if I’m missing anything obvious?”

Assistant Response:
“Your approach is mostly correct. The only thing to confirm is that storage.get("todos") returns an array (which you already handle with || []). Also make sure the tool name matches the key inside your executions object. Other than that, the logic for adding and completing tasks looks fine.”

### Prompt 3
“What’s the correct way to add my API key when deploying?”

Assistant Response:
"Run it from the root of your project (the same folder as wrangler.jsonc). The command is wrangler secret put OPENAI_API_KEY, and after running it, paste your key when it asks for input. Wrangler will store it securely for deployments."

---

These prompts were used for learning and debugging while implementing the project.
