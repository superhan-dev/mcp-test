# MCP Test Project

This repository is a test project for Model Context Protocol (MCP) integration with Supabase.

## Project Structure

```
├── supabase/
│   └── config.toml    # Supabase configuration
└── .gitignore        # Git ignore rules
```

## Setup

1. Clone the repository:

```bash
git clone https://github.com/superhan-dev/mcp-test.git
```

2. Configure Supabase:
   - Set up your Supabase access token in VS Code
   - Update the configuration in `supabase/config.toml` as needed

## Development

This project uses:

- Supabase for backend services
- Model Context Protocol (MCP) for integration

## Environment Variables

The following environment variables are required:

- `SUPABASE_ACCESS_TOKEN`: Your Supabase access token
