# clearning_playwright — Project Context

## Thông tin dự án (Project Info)
- **Tên dự án:** clearning_playwright
- **Loại kiểm thử:** Functional
- **Môi trường:** STG
- **URL:** TBD
- **Team:** Solo
- **QC phụ trách:** hattm

## Version Info
- **Current version:** v1.0
- **Version history:** v1.0 (initial)
- **MASTER-MEMORY:** `02_analyze-requirements/MASTER-MEMORY.md`
- **Project Rules:** `02_analyze-requirements/Project_rule.md`

## Quy trình làm việc (Workflow)
```
00_input/v1.0/ (tài liệu gốc)
  → 01_test-plans/ (create-test-plan)
    → 02_analyze-requirements/v1.0/ (analyze-requirements)
      → 03_test-cases/v1.0/ (generate-tc → consolidate → TC-MASTER)
        → 11_tc-review/ (review-tc + review-src-tc)
          → 08_test-runs/ (execute)
            → 05_bug-reports/ (log bugs)
              → 09_reports/ (summary report)

Nếu có automation:
  → 10_source-code/ (scan-source → implement-auto)
  → 11_tc-review/ (review-src-tc: compare TC ↔ code)
  → execute-maintain → log-bug → test-report
```

## MEMORY Files
- **MASTER-MEMORY:** `02_analyze-requirements/MASTER-MEMORY.md` — cross-version registry
- **Version MEMORY:** `02_analyze-requirements/v1.0/MEMORY.md` — version-scoped analysis
- **Source-code MEMORY:** `10_source-code/MEMORY.md` — locators, page classes, implementation log

## Naming Conventions
- Documents: `DOC-v[VERSION]-[NN]`
- Scenarios: `SC-[MODULE]-[NNN]`
- Test cases: `TC-[MODULE]-[NNN]`
- TC Master: `TC-MASTER-v[VERSION].xlsx`
- Bug reports: `BUG-[NNN]-[short-title].md`
- Test runs: `TR-v[VERSION]-[YYYY-MM-DD].md`
- Reports: `REPORT-[TYPE]-v[VERSION]-[DATE].md`

## Folder Reference
| # | Folder | Mục đích | Skill liên quan |
|---|--------|----------|----------------|
| 00 | input/v1.0/ | Tài liệu đầu vào (theo version) | analyze-requirements |
| 00 | input/shared/ | Tài liệu dùng chung | analyze-requirements |
| 01 | test-plans/ | Test plan tổng thể | create-test-plan |
| 02 | analyze-requirements/ | MASTER-MEMORY + Project_rule | analyze-requirements |
| 02 | analyze-requirements/v1.0/ | Analysis output theo version | analyze-requirements |
| 03 | test-cases/v1.0/ | TC-MASTER + fragments | generate-tc |
| 04 | test-data/ | Dữ liệu test | — |
| 05 | bug-reports/ | Báo cáo lỗi | log-bug |
| 06 | checklists/ | Smoke + release checklists | — |
| 07 | environments/ | Config môi trường | — |
| 08 | test-runs/ | Logs chạy test (+ vibe/) | test-report, vibe-test |
| 09 | reports/ | Báo cáo tổng hợp | test-report |
| 10 | source-code/ | Automation code + MEMORY | scan-source, implement-auto |
| 11 | tc-review/ | Review reports (TC + SRC-TC) | review-tc, review-src-tc |

## Automation
- **Framework:** Playwright + TypeScript
- **Source code:** root repo (`playwright.config.ts`, `tests/`) — `10_source-code/` để tracking
- **MEMORY (source-code):** `10_source-code/MEMORY.md`

## Project Rules
→ Xem chi tiết: `02_analyze-requirements/Project_rule.md`

## Tools
- QA project scaffolded by `init-project` skill
- Framework: Multi-Version (MASTER-MEMORY enabled)
- PIPELINE.md và COMMANDS.md ở root — tester đọc COMMANDS.md để biết cách gọi skill.
- Created on: 2026-06-28
