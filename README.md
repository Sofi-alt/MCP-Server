# MCP-Server

In the following repository for the thesis work on the **Model Context Protocol (MCP) for the Open Data Portals** (namely CKAN, DKAN, OpenDataSoft, and Socrata), I present a simple integration for the implementation involving NL queries/question answering.

**Evaluation Framework:**
1) Using **pytest custom modules** for custom written queries on basis of selected **topics/tags**

OR | AND

2) **Text-to-SQL Benchmarks** eg. **TACO** (Benchmark mirroring real-time application with ambiguous and multi-database queries with provided gold standard answers/ 2 main datasets collections).

## Possible Architectural Structure (High Level)
Model Context Protocol simplified implementation would incorporate all 3 main components in interconnected way with reference of prompts and resources within the main tool implementation calls (ref. using as "helpers"), Remote MCP server using Streamable HTTP eg. "..., host = "127.0.0.1", port = 8000": *1) Tools; 2) Prompts; 3) Resources;*
  
### 1. Tools (3 main functional tools)
Implementation of the below provided tools can be accomplished either via if/else integration of the dictionary containing specifications on the callable APIs for CKAN/DKAN/Socrata/OpenDataSoft portal endpoints ( with 



### 2. Prompts



### 3. Resources
