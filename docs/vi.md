# Nền tảng công cụ kịch bản — tệp kịch bản cho các trình sửa

`scenario_tools_base` là thư viện dùng chung của các trình sửa đọc hoặc ghi tệp kịch bản. Nó không thêm cửa sổ và được cài cùng các trình sửa cần đến nó.

## Ai dùng nó

Trình sửa kịch bản, trình sửa cảnh, trình sửa tương tác và ánh sáng, và trình sửa bản đồ RPG.

## Nó cung cấp gì

- **`ScenarioFileService`** — tìm các tệp `.scenario` của mọi mod (`ScanScenarioFiles`), đọc và ghi chúng (chỉ mod dạng thư mục), phân tích phần đầu (cảnh, độ ưu tiên), trích tham chiếu (chuyển cảnh, khóa bản địa hóa, nhiệm vụ, nền), tạo kịch bản mới cho một cảnh (`CreateForScene`) và dựng đồ thị cảnh (`BuildSceneGraph`, dữ liệu cho đồ thị của trình sửa kịch bản).
- **`ScenarioSyntaxService`** — tô sáng ngôn ngữ kịch bản trong ô văn bản của các trình sửa (trình sửa bản đồ RPG dùng nó cho kịch bản sự kiện) và tách dòng lệnh thành từ; nhờ nó trình sửa tương tác tìm ra kịch bản nào thêm một vật tương tác, còn trình sửa ánh sáng đọc và ghi lại dòng `light_set` bằng dịch vụ tệp.

Bản thân ngôn ngữ đến từ bộ máy hội thoại (`dialog_base`); các dịch vụ tệp và cảnh trung lập nằm ở `tools_base`, nên công cụ không đụng đến kịch bản sẽ không kéo theo bộ máy hội thoại.

## Phụ thuộc

`tools_base`, `dialog_base`.
