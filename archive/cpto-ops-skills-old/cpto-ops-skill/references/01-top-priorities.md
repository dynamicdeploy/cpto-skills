# Reference: Top Priorities Framework

## Purpose
Establish the strategic priority stack for a product/company. This is always the FIRST artifact
produced. Every execution task, launch item, and OE metric must map to a priority here.

## Source Template
Based on `Lumenci_Execution_Strategy_and_Plan.xlsx → 'Top Priorities'` tab.

## Schema

| Column | Type | Description |
|--------|------|-------------|
| Number | Integer | Sequential priority rank (1 = highest) |
| Priority | String | Name of the strategic priority |
| Category | Enum | Strategy \| Engineering \| Product \| GTM \| Operations \| Security \| AI/Agentic |
| Status | Enum | Not Started \| In Progress \| On Hold \| Blocked \| Done |
| Owner | String | Name or role of accountable person |
| Launch Date | Date | Target completion or launch date |
| Notes | String | Context, dependencies, or blockers |

## CPTO Priority Categories

### Strategy Priorities
- Market positioning and competitive differentiation
- Strategic partnerships and ecosystem plays
- Investor/board mandates

### Engineering Priorities
- Architecture modernization
- Technical debt reduction
- Platform reliability / SLO improvements

### Product Priorities
- Core feature development
- UX/design improvements
- Customer-requested capabilities

### GTM Priorities
- New segment entry
- Pricing & packaging changes
- Sales enablement and field readiness

### Operations Priorities
- Process standardization
- Team structure and hiring
- Tooling and infrastructure

### Security Priorities
- Compliance certifications (SOC2, ISO 27001)
- Vulnerability backlog
- Security posture improvements

### AI/Agentic Priorities
- AI feature development
- Agentic workflow automation
- LLM integration and cost optimization

## Excel Generation Instructions

```python
from openpyxl import Workbook
from openpyxl.styles import Font, PatternFill, Alignment, Border, Side
from openpyxl.utils import get_column_letter

# Sheet name: "Top Priorities"
# Columns: A=Number, B=Priority, C=Category, D=Status, E=Owner, F=Launch Date, G=Notes

# Header styling: navy fill, white bold text
# Status column: use data validation dropdown
# Conditional formatting on Status: color-code by value

# Status color map:
STATUS_COLORS = {
    "Done":        "70AD47",  # Green
    "In Progress": "FFD966",  # Yellow  
    "On Hold":     "F4B942",  # Orange
    "Blocked":     "FF0000",  # Red
    "Not Started": "BFBFBF",  # Gray
}

# After user provides priorities, populate rows with their data
# Sort by Number (ascending)
# Apply borders to all data cells
# Freeze row 1
```

## How To Populate From User Input

Ask the user:
1. "What are your top 5-10 strategic priorities for this product?"
2. "Who owns each priority?"  
3. "What is the target date for each?"
4. "Which category does each fall under?"

If user is vague, use the CPTO framework to suggest defaults based on their product phase:
- **Pre-Product**: Strategy, Product, GTM
- **MVP**: Product, Engineering, GTM
- **Growth**: Engineering, GTM, Operations
- **Scale**: Engineering, Security, Operations, AI/Agentic
- **Enterprise**: Security, Operations, AI/Agentic, GTM

## Output Validation Checklist
- [ ] Every priority has an owner (no "TBD" acceptable)
- [ ] Every priority has a date (approximate is fine, but required)
- [ ] At least 1 Engineering priority present
- [ ] At least 1 GTM/Product priority present
- [ ] No more than 10 priorities (focus requires constraint)
- [ ] Priorities are numbered 1-N (no gaps)
