# 🤖 Chat Agent - Mariam Custom AI Assistant (to do list)

This is a customized version of the Cloudflare Agents Starter Template, extended to include additional tools such as a to-do list
The project demonstrates how to build a fully functional AI-powered assistant using Cloudflare Workers, Durable Objects, and the Agents API.

## 🚀 Live Demo  
You can try the deployed version here:

👉 **https://blue-glitter-f486.ten22011.workers.dev/**

To try the components added to this AI assistant, you can ask the bot to add tasks to your to-do list, list everything currently in your to-do list, or mark a task as completed. Just type naturally in the chat and the agent will guide you through each action.
<img src="https://raw.githubusercontent.com/mariamseljaas/cf_ai_chatbot_Mariam/master/pic.png" width="400">

## Features
- 📝 Custom To do List Tool (add/list/complete tasks)
- 💬 Interactive chat interface with AI
- 🛠️ Built-in tool system with human-in-the-loop confirmation
- 📅 Advanced task scheduling (one-time, delayed, and recurring via cron)
- 🌓 Dark/Light theme support
- ⚡️ Real-time streaming responses
- 🔄 State management and chat history
- 🎨 Modern, responsive UI

## Prerequisites

- Cloudflare account
- OpenAI API key



## Project Structure

```
├── src/
│   ├── app.tsx        # Chat UI implementation
│   ├── server.ts      # Chat agent logic
│   ├── tools.ts       # Tool definitions
│   ├── utils.ts       # Helper functions
│   └── styles.css     # UI styling
```

## Customization Guide
This version includes new tools built for this project:

✅ Todo List Tool
Stored inside Durable Object storage.
```ts
/**
 * Add a task to todo list — requires confirmation
 */
const todo_add = tool({
  description: "Add a task to the user's todo list",
  inputSchema: z.object({
    task: z.string()
  })
});

/**
 * List todo tasks — requires confirmation
 */
const todo_list = tool({
  description: "List all the user's todo tasks",
  inputSchema: z.object({})
});

/**
 * Complete a task — requires confirmation
 */
const todo_complete = tool({
  description: "Mark a todo task as completed",
  inputSchema: z.object({
    task: z.string()
  })
});
```


### Example Use Cases
1. **Personal Productivity Assistant (To-do List)**
   - Add tools for:
     - todo_add — add a new task
     - todo_list — list all current tasks
     - todo_complete — mark a task as completed
    
  -Example interactions:
    -“Add a task to my todo list: study for exam”
    -“List my todo tasks”
    -“Mark ‘study for exam’ as completed”
  This functionality uses Durable Object storage to persist tasks across sessions.

2. **Customer Support Agent**
   - Add tools for:
     - Ticket creation/lookup
     - Order status checking
     - Product recommendations
     - FAQ database search

3. **Development Assistant**
   - Integrate tools for:
     - Code linting
     - Git operations
     - Documentation search
     - Dependency checking

4. **Data Analysis Assistant**
   - Build tools for:
     - Database querying
     - Data visualization
     - Statistical analysis
     - Report generation

5. **Personal Productivity Assistant**
   - Implement tools for:
     - Task scheduling with flexible timing options
     - One-time, delayed, and recurring task management
     - Task tracking with reminders
     - Email drafting
     - Note taking

6. **Scheduling Assistant**
   - Build tools for:
     - One-time event scheduling using specific dates
     - Delayed task execution (e.g., "remind me in 30 minutes")
     - Recurring tasks using cron patterns
     - Task payload management
     - Flexible scheduling patterns


## Learn More

- [`agents`](https://github.com/cloudflare/agents/blob/main/packages/agents/README.md)
- [Cloudflare Agents Documentation](https://developers.cloudflare.com/agents/)
- [Cloudflare Workers Documentation](https://developers.cloudflare.com/workers/)

## License

MIT
