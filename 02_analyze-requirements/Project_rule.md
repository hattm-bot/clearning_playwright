# Project Rules — clearning_playwright

> Quy tắc dự án cho pipeline QA. Các skill đọc file này để áp dụng đúng convention.
> Created: 2026-06-28 · QC phụ trách: hattm

## §1. Thông tin chung
| Field | Value |
|-------|-------|
| Project | clearning_playwright |
| Version đầu tiên | v1.0 |
| Môi trường mặc định | STG |
| Loại kiểm thử | Functional |
| Team mode | Solo |
| Ngôn ngữ TC | Tiếng Việt |
| Automation | Playwright + TypeScript |

### §1.2 Naming Conventions
- Documents: `DOC-v[VERSION]-[NN]`
- Scenarios: `SC-[MODULE]-[NNN]`
- Test cases: `TC-[MODULE]-[NNN]`
- TC Master: `TC-MASTER-v[VERSION].xlsx`
- Bug reports: `BUG-[NNN]-[short-title].md`
- Test runs: `TR-v[VERSION]-[YYYY-MM-DD].md`
- Reports: `REPORT-[TYPE]-v[VERSION]-[DATE].md`

## §2. Môi trường (Environments)
| Env | URL | Ghi chú |
|-----|-----|---------|
| STG | TBD | Mặc định cho QA |

## §3. Test Types
- Functional (chính)

## DOC Notation
req_notation: auto
# FR/VR: doc đánh số Functional/Validation Rule (vd kiểu FCP)
# AC:     doc dùng Acceptance Criteria
# UC:     doc dùng Use Case
# US-key: doc dùng User Story key (vd JIRA-123)
# none:   doc không đánh số → traceability dùng DOC-ID §section
# auto:   chưa rõ → analyze-requirements tự phát hiện từ doc ở lần chạy đầu rồi GHI NGƯỢC giá trị thật vào đây

## §10. Custom Rules
> Để trống — bổ sung khi cần.
-
