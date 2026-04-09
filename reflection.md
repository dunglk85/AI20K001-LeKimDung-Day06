# Individual reflection — Lê Kim Dũng

## 1. Role
UI prototype developer + demo script writer + prompt engineer. Phụ trách xây dựng giao diện chatbot, code agent, viết demo script và hỗ trợ prompt engineering.

## 2. Đóng góp cụ thể
- Build UI prototype chatbot bằng Claude Artifacts (HTML/CSS/JS)
- Viết code agent
- Hỗ trợ prompt engineering cho các flow chính

## 3. SPEC mạnh/yếu
- Mạnh nhất:
    + Problem framing rõ ràng: đúng pain CSKH (request lặp lại, high volume).
    + Thiết kế đủ 4 paths: cover cả đúng, không chắc và sai → system robust hơn.
    + Chọn augmentation hợp lý: giảm risk, giữ user trong control.
    + Metric đúng hướng (precision-first): phù hợp domain cần trust cao.
    + Nhận diện đúng failure modes: hallucination, sai intent, thiếu context.

- Yếu nhất:
    + Thiếu eval dataset: chưa có test set & ground truth để đo chính xác.
    + Chưa rõ intent → action: logic gọi FAQ / hỏi thêm / tạo ticket còn mơ hồ.
    + RAG chưa chi tiết: thiếu design về chunking, retrieval, giảm hallucination.
    + Chưa rõ confidence handling: chưa có cách tính và threshold cụ thể.

## 4. Đóng góp khác
- Thiết lập repo github, đảm bảo material chuẩn lên repo 

## 5. Điều học được
AI product ≠ chỉ là model tốt: quan trọng nhất là design flow (happy / low-confidence / failure / correction).
Handling uncertainty quan trọng hơn accuracy: cách AI thể hiện “không chắc” quyết định trust của user.
Precision > Recall trong CSKH: trả lời sai → mất trust, nên ưu tiên đúng hơn là nhiều.
Data flywheel: user correction là dữ liệu để cải thiện hệ thống lâu dài.
Augmentation > Automation: AI nên đề xuất, user quyết định để giảm rủi ro.
## 6. Nếu làm lại
Thiết kế evaluation sớm hơn: tạo test set intent và đo accuracy ngay từ đầu để iterate nhanh.
Tách rõ intent → action: phân biệt bước hiểu intent và bước quyết định hành động (FAQ / hỏi thêm / tạo ticket).
Cải thiện failure handling: thêm confidence score và fallback “không chắc” để tránh trả lời sai mà user không biết.
Nâng cấp RAG: cải thiện chunking, embedding và retrieval để giảm hallucination.
Chuẩn hóa prompt: version control và A/B test prompt thay vì chỉnh thủ công.
Tối ưu UX cho correction: cho phép user sửa intent trực tiếp để thu data sạch hơn.

## 7. AI giúp gì / AI sai gì
- **Giúp:** Dùng Claude Code để sinh code nhanh cho prototype, hỗ trợ viết UI, logic agent và gợi ý prompt.
- **Sai/mislead:** Đôi khi sinh code chạy được nhưng không tối ưu hoặc sai logic edge case; một số gợi ý prompt/flow nghe hợp lý nhưng không đúng với thực tế user behavior nên cần kiểm chứng lại.
