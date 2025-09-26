# 📚 Repository Explorer for Students
*A Simple Guide to Understanding Any Open Source Project*

---

## The Prompt to Use

Copy and paste this into your AI assistant:

```
You are a senior software engineer with deep expertise of the current codebase and patient coding mentor helping a student(me) understand an open source repository.
Analyze this codebase and explain it in simple, system overview language.

Please provide:

## 1. What is This Project? (Overview)
- **Purpose**: What problem does it solve? (1-2 sentences)
- **Main Features**: What can it do? (3-5 bullet points)
- **Tech Stack**: What languages/frameworks does it use?

## 2. Project Structure (Map)
Show me the important folders:
`
project/
├── [main code folder]/     # What's here?
├── [test folder]/          # Testing code
├── [docs folder]/          # Documentation
└── [config files]          # Settings
`

## 3. How It Works (Architecture)
Draw a simple diagram showing the main parts:
`mermaid
graph LR
    User --> Frontend
    Frontend --> Backend
    Backend --> Database
`
Explain each part in 1 sentence.

## 4. Key Files to Start With
List 3-5 files a beginner should read first:
1. `filename.ext` - Why this file matters
2. `filename.ext` - What you'll learn from it
3. `filename.ext` - How it connects to others


## 5. Main Concepts
Explain 3 key main use cases used in this project:
- **Concept 1**: Simple explanation
- **Concept 2**: Simple explanation  
- **Concept 3**: Simple explanation

## 6. Learning Path
If I'm new, what order should I explore?
1. Start here: [file/folder] - because...
2. Then look at: [file/folder] - to understand...
3. Finally explore: [file/folder] - for advanced stuff

## 7. Cool Things & Challenges
- **What's well done**: 2 things this project does nicely
- **What's tricky**: 2 things that might confuse beginners
- **Learning opportunity**: What skill will I develop?

Keep explanations simple, use analogies where helpful, and assume I know basic programming but not advanced concepts.
```

---

## 🎯 When to Use This Prompt

Perfect for:
- **First time** exploring an open source project
- **Class assignments** requiring repo analysis
- **Contributing** to open source as a beginner
- **Learning** how real projects are structured

---

## 💡 Tips for Students

### Before Using the Prompt
1. **Clone the repo** or browse it on GitHub
2. **Read the README** first (if one exists)
3. **Note what confuses you** - ask follow-up questions

### After Getting Results
Ask follow-ups like:
- "Explain [concept] in simpler terms"
- "Show me how [feature] works step by step"
- "What does [specific file] do?"
- "How would I add a simple feature?"

### Making It Even Simpler
If still too complex, add this to your prompt:
`
Explain like I'm a first-year CS student who only knows basic Python/Java.
Use everyday analogies to explain technical concepts.
`

---

## 📝 Example Output Format

Here's what a good response looks like:

### 1. What is This Project?
**Purpose**: This is a to-do list app that helps people organize tasks.

**Main Features**:
- Add and delete tasks
- Mark tasks as complete
- Filter by priority
- Share lists with friends

**Tech Stack**: JavaScript (React for UI, Node.js for server)

### 2. Project Structure
`
todo-app/
├── src/          # Main application code
├── components/   # UI pieces (buttons, forms)
├── server/       # Backend API code
└── package.json  # Project dependencies
`

### 3. How It Works
`mermaid
graph LR
    Browser --> React[React UI]
    React --> API[Node.js API]
    API --> DB[Database]
```
The browser shows the UI, React handles interactions, API processes requests, Database stores tasks.

*...and so on...*

---

## 🔄 Quick Reference Card

Save this for quick repo analysis:

1. **What?** - Purpose and features
2. **Structure?** - Folder organization  
3. **How?** - Basic architecture
4. **Where to start?** - Key files
5. **Run it?** - Setup commands
6. **Concepts?** - Main ideas used
7. **Learning path?** - Order to explore
8. **Assessment?** - Strengths and challenges

---

## 📚 For Your Professor/TA

This prompt helps students:
- ✅ Understand project structure systematically
- ✅ Learn to read real-world code
- ✅ Connect theory to practice
- ✅ Build confidence with open source

Grading can focus on:
- Understanding of architecture
- Ability to identify key components
- Clarity of explanations
- Depth of exploration

---

*Remember: Every expert was once a beginner. Take your time, ask questions, and enjoy exploring! 🚀*