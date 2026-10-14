# [Bài tập] Tái cấu trúc mã CSS cho sẵn

Dự án tái cấu trúc mã nguồn CSS và HTML từ repository mẫu [codegym-vn/responsive-grid](https://github.com/codegym-vn/responsive-grid) sang kiến trúc SASS/SCSS module hóa, loại bỏ hoàn toàn các thuộc tính inline style lộn xộn.

---

## 1. Cải tiến chính sau khi tái cấu trúc
- **Loại bỏ inline styles**: Chuyển toàn bộ các thuộc tính `style="..."` sang các class BEM và tiện ích SASS có ngữ nghĩa.
- **Biến màu sắc & lưới (`abstracts/_variables.scss`)**: Tách màu header (`#9933cc`), footer (`#0099cc`), item (`#33b5e5`), và tính toán tự động chiều rộng 12 cột lưới (`calc(100% / 12)`).
- **Mixins linh hoạt (`abstracts/_mixins.scss`)**: Mixin tính toán độ rộng theo số cột `@mixin col-span($cols)`, xử lý float bằng `@mixin clearfix`.
- **Cấu trúc thư mục chuẩn**:
  - `abstracts/`: Chứa biến và mixins.
  - `base/`: Reset CSS và typography.
  - `layout/`: Bố cục lưới, container, wrapper, item block.
  - `main.scss`: Tập trung import và quản lý toàn bộ hệ thống.

---

## 2. Cấu trúc thư mục dự án
```
tai-cau-truc-ma-css-responsive-grid/
├── abstracts/
│   ├── _variables.scss
│   └── _mixins.scss
├── base/
│   └── _reset.scss
├── layout/
│   └── _grid.scss
├── main.scss
├── main.css
├── main.css.map
├── index.html            # File HTML hoàn thiện sau khi tái cấu trúc
├── responsive_grid.htm   # File gốc của CodeGym để đối chiếu
├── package.json
└── README.md
```

---

## 3. Lệnh biên dịch
```bash
# Biên dịch SASS
sass main.scss main.css

# Tự động theo dõi
sass main.scss main.css --watch
```
