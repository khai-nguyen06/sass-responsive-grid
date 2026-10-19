# responsive-grid-sass

Tái cấu trúc mã CSS của [codegym-vn/responsive-grid](https://github.com/codegym-vn/responsive-grid) sang SASS.

## Những gì đã thay đổi

- **Tách inline style và thẻ `<style>`** ra file SCSS riêng, HTML chỉ còn class.
- **Biến** (`abstracts/_variables.scss`): màu sắc, độ rộng cột, viền, khoảng cách, độ mờ.
- **Map + `@each`** (`$wrapper-heights`): tự sinh các modifier `--header`, `--body`, `--footer`, `--guides` cho chiều cao hàng.
- **Mixins** (`abstracts/_mixins.scss`): `full-width-column`, `plain-cell`, `block-size`, `row-height`.
- **Nesting**: `&--modifier`, `&:first-child`, `&:last-child`.
- **Partials** theo thư mục `abstracts`, `base`, `layout`, `components`, gộp trong `main.scss`.
- Bỏ khai báo `background-color: #84c754` bị ghi đè ngay sau đó bởi `#f1f1f1` (code thừa).

Giao diện hiển thị giống hệt bản gốc.

## Cấu trúc thư mục

```
responsive-grid-sass/
├── original/
│   └── responsive_grid.htm   # Bản gốc để đối chiếu
├── scss/
│   ├── abstracts/
│   │   ├── _variables.scss
│   │   └── _mixins.scss
│   ├── base/
│   │   └── _reset.scss
│   ├── layout/
│   │   └── _grid.scss
│   ├── components/
│   │   ├── _grid-content.scss
│   │   └── _blocks.scss
│   └── main.scss
├── css/
│   └── main.css              # CSS biên dịch
├── index.html
└── package.json
```

## Biên dịch

```bash
npm install
npm run build   # scss/main.scss -> css/main.css
npm run watch   # tự động biên dịch khi lưu file
```

Sau đó mở `index.html` trong trình duyệt.
