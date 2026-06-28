# COMMANDS — clearning_playwright

> Tester chỉ cần đọc file này: copy-paste lệnh để gọi từng skill.
> Solo mode · Automation: Playwright + TypeScript · Version hiện tại: v1.0

## 0. Setup (đã xong)
```
/init-project        # ✅ đã scaffold project này
```

## 1. Test Plan
```
/create-test-plan          # tạo test plan cho release/feature
```

## 2. Phân tích yêu cầu
```
# Đặt tài liệu vào 00_input/v1.0/ trước, rồi:
/analyze-requirements --init @00_input/v1.0/
/analyze-requirements --update      # khi có thay đổi / version mới
/analyze-requirements --sweep       # rà lượt 2 tìm requirement bỏ sót
```

## 3. Sinh Test Case
```
/generate-tc                        # standard 1-1 mapping (default)
/generate-tc --comprehensive        # áp dụng 8 kỹ thuật thiết kế TC (B1-B8)
/generate-tc --techniques EP,BVA,DT # selective: chỉ vài kỹ thuật
/generate-tc --consolidate          # gộp fragments → TC-MASTER
```

## 4. Review Test Case
```
/review-tc                          # review chất lượng TC-MASTER (score 0-100)
```

## 5. Automation
```
/init-source-code --archetype playwright-ts   # (tùy chọn) scaffold lại source POM chuẩn
/scan-source-code                              # index source → 10_source-code/MEMORY.md
/implement-automation                          # code test từ TC-MASTER
```

## 6. Review Source ↔ TC
```
/review-src-tc                      # so sánh TC-MASTER vs code, tìm mismatch
```

## 7. Chạy test
```
/vibe-test                          # AI chạy TC qua MCP (Playwright)
/execute-maintain                   # chạy automation thật, classify fail
```

## 8. Bug
```
/log-bug                            # tạo / cập nhật bug report
```

## 9. Báo cáo
```
/test-report                        # tổng hợp report + GO/NO-GO
```

## 10. Kiểm tra sức khỏe dữ liệu
```
/health-check                       # quick consistency check (MEMORY files)
/health-check --full                # + parse TC-MASTER Excel, ghi report
/health-check --version v1.0        # check 1 version
```

## Tiện ích (ngoài pipeline)
```
/fetch-us                           # kéo User Story từ Jira (cần cấu hình Jira)
```

## Luồng khuyến nghị
```
/create-test-plan
  → (đặt tài liệu vào 00_input/v1.0/) → /analyze-requirements --init
    → /generate-tc → /generate-tc --consolidate → /review-tc
      → /scan-source-code → /implement-automation → /review-src-tc
        → /vibe-test hoặc /execute-maintain
          → /log-bug
            → /test-report
```
