# Architecture Overview

The project uses **Medallion Architecture**:

1. **Bronze Layer:** Raw CSVs from GitHub ingested into Lakehouse tables
2. **Silver Layer:** Cleaned and enriched data with validations
3. **Gold Layer:** Domain-specific tables:
   - Doctors: `gold_doctors_data`
   - Nursing: `gold_nursing_data`

**Notes:** All layers reside in the same Lakehouse, domains share only authorized tables.
