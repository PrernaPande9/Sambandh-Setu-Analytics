# Project Documentation: Sambandh Setu Analytics

## 1. Objective
Provide a single-page view of relationship progression: how many users and connections exist, where connections stall or drop, what topics cause friction, and how ready and family-involved the parties are.

## 2. Audience
Product and operations teams who need to improve conversion through the journey stages.
## 3. Data Sources
The analytics data layer is derived from five relational CSV tables modeled into an enterprise Star Schema:
- `Fact_ReadinessCheck.csv`: Granular telemetry interaction logs and topic evaluation outcomes.
- `Dim_JourneyStage.csv`: 6 chronological progression stages and sorting keys.
- `Dim_DiscussionTopic.csv`: Discussion domains (Family Expectations, Location, Lifestyle, Finances, etc.).
- `Dim_Connection.csv`: Active cohort IDs and connection states (Active, Paused, Completed).
- `Dim_User.csv`: Anonymized user demographic attributes.

## 4. Dashboard Layout (1280 × 720 Canvas)
- **Header:** Title banner (*Sambandh Setu | Relationship Progression & Telemetry Analytics*)
- **Row 1 (KPI Ribbon):** 5 single-value metric cards and a multi-select **Connection Status** dropdown slicer.
- **Row 2 (Upper Quadrant):**
  - Left: *Stage Conversion & Drop-off Waterfall* (Matrix showing stage volumes and step fallouts).
  - Right: *Active Cohort Distribution* (Donut chart profiling Active, Paused, and Completed states).
- **Row 3 (Lower Quadrant):**
  - Left: *Stage Volume vs Telemetry Density* (Combo Column/Line chart tracking user action velocity).
  - Right: *Discussion Friction Ranking* (Horizontal bar chart ranking unresolved conflict by topic).

## 5. KPI Definitions

| KPI | Value / Range | Definition & Business Logic |
| :--- | :--- | :--- |
| **Total Users** | 1,000 | Distinct count of registered platform profiles logged in the telemetry layer. |
| **Active Connections** | 297 (59.52%) | Count of connection pairs currently engaging in conversations without paused status. |
| **Mutual Readiness Rate** | 50.45% | Percentage of initiated connections that successfully achieve mutual readiness consensus. |
| **Family Involvement Rate** | 36.00% | Conversion rate of connection pairs that advance into formal family introductions. |
| **Total Events** | 2,000+ | Total discrete micro-action telemetry events recorded across all stages. |
| **Stage Entries** | 499 to 67 | Distinct count of connection cohorts that successfully cross into a specific milestone. |
| **Stage Drop-Off Rate** | 0.00% to 38.24% | Percentage of cohort fallout between consecutive stages; peaks at Family Involvement (38.24%). |
| **Topic Friction Rate** | 39.92% to 49.48% | Percentage of discussions within a topic flagged as Unresolved; led by Family Expectations (49.48%). |
| **Avg Events Per Connection** | 1.0 to 2.2 | Telemetry density index measuring average micro-actions invested per active connection cohort. |

## 6. Assumptions and Limitations
- **Data Provenance:** The dataset is fully synthetic and anonymized, modeled specifically to simulate real-world relationship progression and micro-action telemetry patterns.
- **Stage Progression Model:** Assumes sequential progression through the 6 journey milestones without direct stage skipping.
- **Cohort Granularity:** Aggregated at the connection-pair level rather than individual user message timestamps.

## 7. Product Recommendations & Next Steps
- **Pre-Family Preparation Module:** Deploy structured mediation checklists before Stage 5 to mitigate the 38.24% churn cliff.
- **Targeted Conversation Prompts:** Introduce algorithmic resolution aids for high-friction topics (*Family Expectations* and *Location*) to unblock paused relationships.
- **Automated Re-engagement Nudges:** Trigger inactive cohort check-ins after 5–7 days of silence to reactivate stalled discussions (27.05% Paused state).