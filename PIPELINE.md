# PIPELINE — clearning_playwright

> Quy trình QA 13 bước, version-aware. Mỗi skill đọc/ghi MEMORY files để giữ nhất quán.
> Status protocol: NOT_STARTED → IN_PROGRESS → PARTIAL → COMPLETED (hoặc FAILED).
> Created: 2026-06-28 · Version hiện tại: v1.0 · Automation: Playwright + TypeScript (yes)

## Skill Registry

| # | Skill | Command | Vai trò | Folder sở hữu |
|---|-------|---------|---------|---------------|
| 1 | init-project | `/init-project` | Scaffold project structure | root, 00_–11_ |
| 2 | create-test-plan | `/create-test-plan` (`/test-plan`) | Test plan tổng thể | 01_test-plans/ |
| 3 | analyze-requirements | `/analyze-requirements` (`/analyze`) | Phân tích yêu cầu → scenario map, MASTER-MEMORY | 02_analyze-requirements/ |
| 4 | generate-tc | `/generate-tc` | Sinh TC Excel + TC-MASTER | 03_test-cases/ |
| 5 | review-tc | `/review-tc` | Review chất lượng TC | 11_tc-review/ |
| 6 | scan-source-code | `/scan-source-code` (`/scan-source`) | Index source automation → MEMORY | 10_source-code/ |
| 7 | implement-automation | `/implement-automation` (`/implement`) | Code POM từ TC-MASTER | 10_source-code/ |
| 8 | review-src-tc | `/review-src-tc` | So sánh TC ↔ code | 11_tc-review/ |
| 9 | vibe-test | `/vibe-test` (`/vibe-web`, `/vibe-mobile`) | Chạy TC qua MCP (AI manual tester) | 08_test-runs/vibe/ |
| 10 | execute-maintain | `/execute-maintain` (`/execute`) | Chạy automation, classify fail | 10_source-code/ §15-16 |
| 11 | log-bug | `/log-bug` | Tạo & quản lý bug | 05_bug-reports/ |
| 12 | test-report | `/test-report` (`/report`) | Báo cáo stakeholder + GO/NO-GO | 09_reports/ |
| 13 | health-check | `/health-check` | Cross-cutting consistency validator | 09_reports/ |

> Utility (ngoài pipeline 12 bước): `/fetch-us` (kéo US từ Jira), `/init-source-code` (scaffold source archetype).

## Pipeline Flow

```
init-project ✅
  → create-test-plan
    → analyze-requirements  (cần 00_input/v1.0/ có tài liệu)
      → generate-tc → review-tc
        → scan-source-code → implement-automation → review-src-tc
          → vibe-test / execute-maintain
            → log-bug
              → test-report

health-check: chạy bất kỳ lúc nào để validate consistency.
```

## §8. Pipeline Status (v1.0)

| # | Skill | Status | Last Run | Mode | Kết quả | Ghi chú |
|---|-------|--------|----------|------|---------|---------|
| 1 | init-project | COMPLETED | 2026-06-28 | — | Scaffold v1.0 | Automation = Playwright TS |
| 2 | create-test-plan | NOT_STARTED | — | — | — | — |
| 3 | analyze-requirements | NOT_STARTED | — | — | — | Chờ tài liệu 00_input/v1.0/ |
| 4 | generate-tc | NOT_STARTED | — | — | — | — |
| 5 | review-tc | NOT_STARTED | — | — | — | — |
| 6 | scan-source-code | NOT_STARTED | — | — | — | Source ở root repo |
| 7 | implement-automation | NOT_STARTED | — | — | — | — |
| 8 | review-src-tc | NOT_STARTED | — | — | — | — |
| 9 | vibe-test | NOT_STARTED | — | — | — | — |
| 10 | execute-maintain | NOT_STARTED | — | — | — | — |
| 11 | log-bug | NOT_STARTED | — | — | — | — |
| 12 | test-report | NOT_STARTED | — | — | — | — |
| 13 | health-check | NOT_STARTED | — | — | — | — |

> Lưu ý: §8 này khởi tạo trong PIPELINE.md. Khi `analyze-requirements` chạy lần đầu, nó tạo
> `MASTER-MEMORY.md` và sao chép/quản lý bảng §8 ở đó (canonical).
