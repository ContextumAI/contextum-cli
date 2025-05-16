# Contextum CLI Tools

Command-line interface tools for managing Contextum MCP server deployments.

## Installation

```bash
npm install -g contextum-cli
```

## Usage

```bash
contextum deploy --image <image-hash>
contextum status --server <server-id>
```

---

#### 5. `src/index.ts`

```ts
#!/usr/bin/env node

import { Command } from 'commander';
const program = new Command();

program
  .name('contextum')
  .description('CLI tool for Contextum MCP server management')
  .version('0.1.0');

program
  .command('deploy')
  .description('Deploy an MCP server')
  .requiredOption('-i, --image <imageHash>', 'Container image hash')
  .action((options) => {
    console.log(`Deploying MCP server with image hash: ${options.image}`);
    // TODO: Implement deployment logic here
  });

program
  .command('status')
  .description('Get status of an MCP server')
  .requiredOption('-s, --server <serverId>', 'Server ID')
  .action((options) => {
    console.log(`Fetching status for server: ${options.server}`);
    // TODO: Implement status check logic here
  });

program.parse();
```
