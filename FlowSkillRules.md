#Flow skill instructions

## Project context
To build flow based integration projects make use of the following resources:
- Built-in services: `config/built-in_services/*.json`.
- Authoritative examples: `.bob/skills/designer-dsl-skill/examples/*/*`.

## ⚠️ CRITICAL: File Organization and Documentation Requirements ⚠️

**EVERY TIME YOU CREATE A .flow FILE, YOU MUST CREATE TWO FILES:**
1. **CREATE A MATCHING .md FILE** - Every `.flow` file MUST have a corresponding `.md` documentation file
2. **ORGANIZE IN pub DIRECTORY** - Both files (`.flow`, `.md`) MUST be created in a subdirectory under `pub/`
3. **SUBDIRECTORY NAME = INTERFACE NAME** - The subdirectory name becomes the `interface` declaration at the top of the `.flow` file

**OPTIONAL: CREATE index.html VIEWER (ONLY WHEN REQUESTED)**
- Create an `index.html` file ONLY when the user specifically requests it
- The HTML viewer displays the `.md` file in a browser with rendered markdown
- Do NOT automatically create `index.html` when creating a flow service

**Project Namespace and Service Invocation:**
- Before you start ask what namespace (project_namespace) needs to be used for the project
- When invoking custom flow services created in this project, use the full namespace path
- **Example**: To invoke the Modulus service: `{project_namespace}.services:Modulus`
- **Example**: To invoke the DecimalToBinary service: `{project_namespace}.services:DecimalToBinary`
- Any `.flow` files in the `pub/` directory can be invoked using this namespace pattern
- Built-in services use the `pub.*` namespace (e.g., `pub.math:addInts`)
- You can only invoke those services defined in `https://github.com/elpinjo/FlowPilot/config/built-in_services/*.json` or those in the workspace in the `pub/` directory
- If a public service isn't well understood, you can read the documentation here: https://www.ibm.com/docs/en/webmethods-integration/wm-integration-server/11.1.0?topic=built-in-services-reference-guide
- Custom project services use the `{project_namespace}.services:` namespace
