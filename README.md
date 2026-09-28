# MCP-Server

In the following repository for the thesis work on the **Model Context Protocol (MCP) for the Open Data Portals** (namely CKAN, DKAN, OpenDataSoft, and Socrata), I present a simple integration for the implementation involving NL queries/question answering.

Documentation used: 
- https://gofastmcp.com/servers/server
- https://modelcontextprotocol.io/docs/2026-07-28/getting-started/intro;

In context of this implementation I would use FastMCP module due to its usability rather than general SDKs official Python specification provided on the MCP Anthropic Documentation.

**Evaluation Framework:**
1) Using **pytest custom modules** for custom written queries on basis of selected **topics/tags**

OR | AND

(2) **Text-to-SQL | Text-to-SPARQL Benchmarks** eg. **TACO** (Benchmark mirroring real-time application with ambiguous and multi-database queries with provided gold standard answers/ 2 main datasets collections). - not really fully viable in sense)

## Possible Architectural Structure (High Level)
Model Context Protocol simplified implementation would incorporate all 3 main components in interconnected way with reference of prompts within the main tool implementation calls (ref. using as "helpers"), Remote MCP server using Streamable HTTP eg. "..., host = "127.0.0.1", port = 8000": **1) Tools; 2) Prompts; 3) Resources;**
  
### 1. Tools 
**3 main functional tools**  with the **main aim of endpoints discovery & schema exploration** within the NL question posed for accurate question/query answering

Implementation of the below provided tools can be accomplished either via if/else integration of the dictionary containing specifications on the callable APIs for CKAN/DKAN/Socrata/OpenDataSoft portal endpoints OR each functional tool written specifically for each API integration (eg. def find_portals_list_ckan..):

1) **Dataset/Portal Search Tool:** responsible for searching for relevant portals by checking listed datasets (DCAT structured properties), groups and tags for the relevant ones based on differentiating catalogue API endpoints, and possibly creating sub-list of pre-filtered relevant datasets for the initially posed natural language question answering.

2) **Schema Exploration:** tool responsible for the metadata extraction from the pre-filtered portals (DCAT, eg. Super-class dcat:Dataset - *distribution*, *spatial/geographic coverage*; Super-class dcat:Resource - *creator, description*, *identifier*, *keyword(s), tag(s)*, *license*, *language*, **theme, category, title, genre**).

3) **Dataset Querying:** dataset querying tool would be responsible for finding relevant data to answer the natural language query within the before-found relevant datasets/endpoints etc., based on the beforehand schema exploration of tags/theme/category/title/genre, extract the information (eg DCAT class Distribution, **access URL, download URL**).

For the authent. reasons, before the exposition of tools with decorators and arguments (on additional descriptive explanation of tool functionality for the correct functionality for the LLM based Client object on the basis of MCP Hist), the function with the "auth = OAuthProxy() would be added".

### 2. Prompts
As general **@mcp.prompt** might be used in my case for the automatic deterministic prompt injection after the tool exposition for the deterministic final answer formulation to guide the final answer, using f""-string to keep all provided final answers in standardised way.

