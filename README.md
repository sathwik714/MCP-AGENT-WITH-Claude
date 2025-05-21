# MCP-AGENT-WITH-Claude
Setting Up Our Environment
Before we dive into implementation, let's install the necessary packages and set up our environment.

Note: For the installation steps, please open a terminal window. These commands should be run in a regular terminal, not in a Jupyter notebook cell.

Step 1: Install uv Package Manager

# Run this in your terminal, not in Jupyter

curl -LsSf https://astral.sh/uv/install.sh | sh

Step 2: Set up the Project
# Create and navigate to a project directory
mkdir mcp-crypto-server
cd mcp-crypto-server
uv init

# Create and activate virtual environment
uv venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
uv add "mcp[cli]" httpx
Running the MCP Server
After we set up the envirnment, we can start build our tools.

Please checkout mcp_server.py to see how to build tools.

now we can start the server by runnning following commands in the ternimal:

# Copy the server file from the scripts folder
cp ../scripts/mcp_server.py .

# Start the MCP server 
uv run mcp_server.py
Integration with Claude Desktop
If you haven't download Claude Desktop, checkout this page.

To connect your MCP server to Claude Desktop:

Step 1: Find the absolute path to your uv command:
which uv
Copy the output (e.g., /user/local/bin/uv or similar)

Step 2: Create or edit the Claude Desktop configuration file:

On macOS: ~/Library/Application Support/Claude/claude_desktop_config.json

On Windows: %APPDATA%\Claude\claude_desktop_config.json


You can checkout this page to see how to create a config file.

Step 3: Add your MCP server configuration: It should be in json 

Replace /ABSOLUTE/PATH/TO/uv with the path you got from the which uv command, and /ABSOLUTE/PATH/TO/GenAI_Agents with the absolute path to your repository.

Step 4: Restart Claude Desktop for the changes to take effect.
You should see  hammer in your chat box.

Claude Desktop connected with MCP

Step 5: Try ask the price of Bitcoin

Type in "What is the current price of Bitcoin ?", and you will get response

Track Bitcoin price with MCP
