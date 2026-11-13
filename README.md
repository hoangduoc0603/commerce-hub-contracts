# commerce-hub contracts

Hợp đồng giữa các service, trung lập ngôn ngữ. Service không chép file từ đây mà dùng package do CI của repo này publish.

| Thư mục | Dùng cho |
|---|---|
| `avro/` | Schema event cho Schema Registry, chia theo service sở hữu (`avro/order/OrderImported.avsc`) |
| `asyncapi/` | Mô tả topic, producer, consumer |
| `openapi/` | API REST của từng service |

CI (sẽ thêm): lint → kiểm tương thích schema (`BACKWARD_TRANSITIVE`: nâng consumer trước, producer sau; field mới luôn có default; đổi phá vỡ thì làm topic mới hậu tố `.v2`. Xem `docs/architecture/08-crosscutting-concepts.md` mục 8.5) → sinh code → publish Maven artifact và npm package có version.
