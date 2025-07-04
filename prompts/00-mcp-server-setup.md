# Prompt #0 V2.0: MCP Server Setup & Configuration

**Version**: 2.0
**Last Updated**: January 2025
**Purpose**: Install and configure all 5 required MCP servers for Claude Code development workflow with enhanced error handling and verification

**Usage**: Run this in Claude Code first before using any other prompts. This sets up the complete MCP environment with robust verification.

```
You need to install and configure 5 essential MCP servers for our development workflow. I'll guide you through each installation with proper verification steps.

**CRITICAL PREREQUISITES:**
- Python and uvx installed (for Serena server)
- Node.js and npm installed (for other servers)
- Claude Code running in your project directory
- Internet connection for package downloads

**STEP 1: Pre-Installation Check**
First, let's verify your current MCP status:

Run: /mcp

If this shows "No MCP servers configured", proceed with installation.
If any servers already exist, note them before continuing.

**STEP 2: Install User-Scoped Servers**
These servers work across all your projects. Install them one at a time:

**2.1 Install Serena (Semantic Code Analysis):**
```bash
claude mcp add serena -s user -- uvx --from git+https://github.com/oraios/serena serena-mcp-server --context ide-assistant
```

After installation, verify with:
```bash
claude mcp list
```
Confirm "serena" appears in the list before proceeding.

**2.2 Install Context 7 (Documentation Access):**
```bash
claude mcp add context7 -s user -- npx -y @upstash/context7-mcp@latest
```

Verify installation:
```bash
claude mcp list
```
Confirm both "serena" and "context7" appear.

**2.3 Install Memory Server (Persistent Context):**
```bash
claude mcp add memory -s user -- npx -y @modelcontextprotocol/server-memory
```

Verify all three user-scoped servers:
```bash
claude mcp list
```
You should see: serena, context7, and memory

**STEP 3: Install Project-Scoped Servers**
These are specific to your current project:

**3.1 Install Filesystem Server:**
```bash
claude mcp add filesystem -s project -- npx -y @modelcontextprotocol/server-filesystem ./src ./tests ./docs ./config
```

Note: If these directories don't exist yet, that's okay - they'll be created during project setup.
To add more directories later, reinstall with additional paths.

**3.2 Install GitHub Server:**
```bash
claude mcp add github -s project -- npx -y @modelcontextprotocol/server-github
```

**STEP 4: Critical Restart Procedure**
The restart is ESSENTIAL - servers won't work without it:

1. Exit Claude Code completely:
   - Press Ctrl+C in terminal, or
   - Type: exit
   - Close the terminal window

2. Wait 5 seconds for complete shutdown

3. Restart Claude Code:
   - Open new terminal
   - Navigate to your project directory
   - Run: claude
   - Wait for "Claude Code is ready" message

**STEP 5: Post-Restart Verification**
This is the most important step - many issues occur here:

Run: /mcp

Expected output should show ALL 5 servers:
```
Available MCP servers:
- serena: connected
- context7: connected
- memory: connected
- filesystem: connected
- github: connected
```

**COMMON ISSUES AND SOLUTIONS:**

**Issue 1: "/mcp shows (no content)" or empty response**
Solution: 
- The restart wasn't complete. Exit Claude Code again
- Wait 10 seconds this time
- Start Claude Code fresh
- Try /mcp again

**Issue 2: "Server shows disconnected"**
Solution:
- Check specific server logs: claude mcp get [server-name]
- For Serena: Verify Python/uvx installation with: python --version && uvx --version
- For npm servers: Verify Node.js with: node --version && npm --version
- Reinstall the specific failed server

**Issue 3: "Command not found" errors**
Solution:
- For uvx: Install with: pip install uvx
- For npx: Comes with npm, verify with: npx --version
- Ensure your PATH includes Python and Node.js binaries

**Issue 4: GitHub server authentication**
Solution:
- This is normal on first use
- Create a GitHub personal access token at: https://github.com/settings/tokens
- When prompted, paste your token
- Token needs repo scope for full functionality

**STEP 6: Install Development Tools**
Install additional tools to enhance your workflow:

**6.1 Claude Code Exporter (Conversation Export Tool):**
```bash
npm install -g claude-code-exporter
```

This tool allows you to export Claude Code conversations for documentation:
- Export prompts, outputs, or full conversations
- Multiple formats: Markdown, JSON, or both
- Aggregate conversations across projects
- Filter by time periods

Verify installation:
```bash
claude-prompts --help
```

**STEP 7: Functional Testing**
Test each server individually:

1. **Filesystem Test:**
   Ask: "List files in the current directory using the filesystem server"
   
2. **Memory Test:**
   Ask: "Remember that my favorite color is blue"
   Then ask: "What's my favorite color?"

3. **Context7 Test:**
   Ask: "use context7 to explain React hooks"

4. **GitHub Test (if in git repo):**
   Ask: "Check git status using the GitHub server"

5. **Serena Test (if you have code files):**
   Ask: "Analyze the code structure using Serena"

6. **Export Tool Test:**
   Run: `claude-prompts --list`
   This should list available conversation sessions

**VERIFICATION CHECKLIST:**
- [ ] All 5 servers show "connected" in /mcp output
- [ ] No error messages in server status
- [ ] Functional tests pass for each server
- [ ] Claude Code was properly restarted after installation
- [ ] Project .mcp.json file created (for project-scoped servers)

**FINAL CONFIRMATION:**
When setup is complete, you should be able to run /mcp and see all 5 servers connected without any errors or empty responses.

DO NOT proceed to other prompts until you have confirmed all servers are working properly. The entire workflow depends on these servers being correctly configured.
```