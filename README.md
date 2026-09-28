# MCP-Server

In the following repository for the thesis work on the **Model Context Protocol (MCP) for the Open Data Portals** (namely CKAN, DKAN, OpenDataSoft, and Socrata), I present a simple integration for the implementation involving NL queries/question answering.

Documentation used: 
- https://gofastmcp.com/servers/server
- https://modelcontextprotocol.io/docs/2026-07-28/getting-started/intro;

In context of this implementation I would use FastMCP module due to its usability rather than general SDKs official Python specification provided on the MCP Anthropic Documentation.

**Evaluation Framework:**
1) Using **pytest custom modules** for custom written queries on basis of selected **topics/tags**

OR | AND

2) **Text-to-SQL Benchmarks** eg. **TACO** (Benchmark mirroring real-time application with ambiguous and multi-database queries with provided gold standard answers/ 2 main datasets collections).

## Possible Architectural Structure (High Level)
Model Context Protocol simplified implementation would incorporate all 3 main components in interconnected way with reference of prompts and resources within the main tool implementation calls (ref. using as "helpers"), Remote MCP server using Streamable HTTP eg. "..., host = "127.0.0.1", port = 8000": **1) Tools; 2) Prompts; 3) Resources;**
  
### 1. Tools 
**3 main functional tools**  with the **main aim of endpoints discovery & schema exploration** within the NL question posed for accurate question/query answering

Implementation of the below provided tools can be accomplished either via if/else integration of the dictionary containing specifications on the callable APIs for CKAN/DKAN/Socrata/OpenDataSoft portal endpoints OR each functional tool written specifically for each API integration (eg. def find_portals_list_ckan..):

1) 



### 2. Prompts



### 3. Resources
