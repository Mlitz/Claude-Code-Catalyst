# Prompt #1 V2.0: Interactive Requirements Discovery

**Version**: 2.0
**Last Updated**: January 2025
**Purpose**: Gather comprehensive project requirements through structured, single-question discovery process with clear guidance and examples

**Usage**: Use this in Claude Code after completing MCP server setup (Prompt #0 V2.0). Provide your initial project idea and Claude will systematically build a complete specification.

```
You have access to 5 MCP servers configured in Prompt #0 V2.0. I need to gather comprehensive requirements for your project through systematic questioning.

**CRITICAL RULES FOR THIS PROCESS:**
1. Ask ONLY ONE question at a time - never multiple questions
2. Wait for the user's complete response before asking the next question
3. Build progressively from general to specific details
4. Store each answer in memory server for context building
5. Adapt questions based on previous answers
6. Focus on actionable, development-ready requirements

**QUESTION PROGRESSION FRAMEWORK:**

Phase 1: Core Understanding (Questions 1-5)
- Project vision and primary goal
- Target users and their main pain points
- Core functionality (3-5 key features)
- Success metrics
- Timeline and constraints

Phase 2: Technical Foundation (Questions 6-10)
- Preferred technology stack (or let me recommend)
- Integration requirements
- Data persistence needs
- Performance requirements
- Security considerations

Phase 3: User Experience (Questions 11-15)
- User interface preferences
- Workflow and user journeys
- Error handling expectations
- Accessibility requirements
- Multi-platform needs

Phase 4: Development Process (Questions 16-20)
- Testing strategy preferences
- Deployment environment
- Monitoring and logging needs
- Documentation requirements
- Maintenance considerations

**MEMORY SERVER USAGE:**
After each answer, I'll store:
- Key decisions made
- Technical choices
- Constraints identified
- Dependencies discovered
- Risk factors

**OUTPUT GOALS:**
By the end of our discussion, we'll have gathered everything needed to create:
- Complete technical specification (spec.md)
- AI development context (claude.md)
- Project roadmap with phases
- Risk assessment and mitigation strategies
- Clear success criteria

**STARTING THE PROCESS:**
I'll begin by understanding your project at a high level, then progressively dive deeper into technical details, always asking one focused question at a time.

Let me start with the first question:

**Question 1:** In one or two sentences, what is the core problem your project aims to solve, and who will primarily benefit from this solution?

[YOUR ANSWER HERE]

---
Note: After you answer, I'll ask the next question based on your response, continuing until we have a complete picture of your project requirements.
```