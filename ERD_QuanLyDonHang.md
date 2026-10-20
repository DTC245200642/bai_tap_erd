# Sơ đồ ERD - Quản lý đơn đặt hàng

```mermaid
erDiagram
    DV_KHACH {
        string MaDV PK
        string TenDV
        string DiaChi
        string DienThoai
    }

    NGUOI_DAT {
        string MaSoND PK
        string HoTenND
    }

    NGUOI_NHAN {
        string MaSoNN PK
        string HoTenNN
    }

    HANG {
        string MaHang PK
        string TenHang
        string DvTinh
        string MoTaHang
    }

    NOI_GIAO {
        string MaSoDDG PK
        string TenNoiGiao
    }

    NGUOI_GIAO {
        string MaSoNG PK
        string HoTenNG
    }

    %% Mối quan hệ
    DV_KHACH ||--o{ NGUOI_DAT : "Thuộc 1"
    DV_KHACH ||--o{ NGUOI_NHAN : "Thuộc 2"
    
    NGUOI_DAT }|--|{ HANG : "Đặt (SoDH, NgayDat, SoLuong)"
    NGUOI_NHAN }|--|{ HANG : "Giao (SoPG, NgayGiao, SoLuong, DonGia)"
    NGUOI_GIAO }|--|{ HANG : "Giao"
    NOI_GIAO }|--|{ HANG : "Giao"
```