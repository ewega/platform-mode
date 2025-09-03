# Platform Mode

Platform Mode is designed to provide a tailored chat experience specifically for platform engineering tasks. By enabling a custom mode, teams can streamline workflows, automate repetitive processes, and ensure consistent application of best practices across infrastructure and development operations. This focused environment helps platform engineers collaborate efficiently, manage complex systems, and accelerate delivery while maintaining high standards of reliability and security.

This code is designed to support a custom chat mode tailored for integration with modern Azure-based reference architectures,
such as the one described at https://humanitec.com/reference-architectures/azure. In such architectures, organizations leverage
a combination of Azure-native services (e.g., Azure Kubernetes Service, Azure DevOps, Azure Active Directory, and managed databases)
alongside developer tooling for streamlined CI/CD, infrastructure automation, and secure, scalable application delivery.
 
The need for a custom chat mode arises from the complexity and diversity of tools and workflows present in these environments.
By providing a specialized chat interface, this code enables:
  - Context-aware assistance for developers and operators working within Azure-centric cloud-native stacks.
  - Integration with deployment pipelines, infrastructure-as-code, and monitoring solutions common in the reference architecture.
  - Enhanced collaboration and troubleshooting by surfacing relevant information and automating routine queries or actions.

This approach helps bridge gaps between development, operations, and security teams, ensuring that communication and automation
are aligned with the best practices and patterns established in the Azure reference architecture.
 
## Structure and files

### Prompts (Slash Commands)

Custom reusable prompts in VS Code/GHCP are incredibly useful and powerful.  They are also referred to as slash commands, essentially invokable prompts you can call upon from the GHCP chat UI by typing "```/```" and a list of commands will appear.  These files must be stored in the .github/prompts directory and have a file extension of *.prompt.md.  The command is then available by typing ```/%file-name%``` in chat.

These commands can also be referenced in other files by telling GHCP to follow either markdown file link syntax ```[some-file-name.prompt.md](.github/prompts/%file-name%.prompt.md)``` or the ```#file:.github/prompts/%file-name%.prompt.md``` syntax.

For the purposes of "Platform Mode" - these prompt commands can be used either to execute the specific command/prompt or referenced and used as part of GHCP custom instructions, custom chat modes or via the ```AGENTS.md``` file to guide an agent to follow a series of steps with higher consistency in executing those tasks.

### Custom Instructions

Custom instructions are rules that are either always executed or scoped to a specific list of file types/extensions via the ```applyTo:``` property in the YAML frontmatter of a custom instruction.  This allows you to ensure that GHCP will always keep certain rules in mind when running all tasks/requests/prompts or only on specific file types.  As an example, we have included an example of a custom instruction for writing Terraform.

Note: Just as you can with custom prompts/slash commands, you can reference custom instructions using the same markdown or #file syntax such that custom Chat Modes can refrence and ensure that specific instructions are always included in the workflow.  This is handy when the file is net new - meaning it does not yet exist in your workspace and hense the rules do not run yet.  Custom Instructions ```applyTo:``` YAML frontmatter property filtering only applies to existing files and not net new files that GitHub Copilot is creating as part of its current tasks.

### Custom Chat Modes

Custom Chat Modes helps to further refine and ground GHCP into a specific "mindset"/role/persona etc. and can constrain it to a certain set of tools (built-in function/tool/mcp capabilities it can call), as well as the model to use for a given task as some are better at reasoning/planning vs. pure coding tasks.  In Platform Mode this allows you to scope and then switch your given Platform Engineering tasks to things like, writing IaC with Terraform, Troubleshooting/Debug Platform Errors/Issue, Write Root Cause Analysis docs and reports etc. and provide it only with the tools that fit for that task (e.g. writing/editing to file system may not be pertinent tool to include to getting resources/error logs from Azure).  This helps to prevent overloading GHCP or any coding assistant from dynamically deciding which tool to use when there could be multiple overlapping or potentially ambiguous tools to leverage for a given task.  Also as of writing this project (Sept 3rd, 2025), there is a 128 tool limit that a given GHCP interaction can have access to.  Even if/when this limit is lifted - it is still good practice to ensure that your agent is limited to a known set of tools to call for a given custom chat mode.

Our custom chat mode is most powerful when we combine the role/task persona for that chat mode as well as knowing our Platform Standards, Instructions/Rules and the Commands/Prompts to which it is to leverage to execute specific tasks (e.g. writing Terraform Module, creating a PRD or SRD or how to execute tasks/todos).  As such a Chat Mode today is the highest level of organizing our workflow and the best way to ensure that we can keep our coding agent on task with out having to rewrite each time or to manually/explicitly ask it to execute prompts/commands in series.  You can set a general high level ask with in a given work domain (e.g. creating a terraform module) and point it towards your ```.platform/standards/``` directory where you will host your orgnaizations Terraform best practices/style guide etc.  We will discuss Platform-Mode specific files and structure next.

## Platform Mode Specific Files

Currently as of Sept 3, 2025, this is in flux and an experiment.  The structure of this is based off of @buildermethods [agent-os](https://github.com/buildermethods/agent-os) for general software development - which would encompas platform engineering in general but we can forsee a point where our naming convension and file structures may differ and become more domain specfic to Platform Engineering.  We would also imagine that we'd include specific chat modes or prompts/slash commands which can call/execute a GitHub Action via MCP as well instead of using an IDP/Platform Engineering Portal...something like Backstage or Azure Dev Center/Deployment Environments.

Already I can imagine that including an Architecture directory as well as a Security, Policy/Governance standards docs into the mix as well.

### Standards

### Products

### Specs