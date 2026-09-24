# quan-ly-don-dat-hang
```mermaid
erDiagram
    DON_VI_KHACH ||--o{ NGUOI_DAT : "quản lý"
    DON_VI_KHACH ||--o{ DON_DAT_HANG : "lập"
    DON_DAT_HANG ||--|{ CHI_TIET_DON_HANG : "chứa"
    HANG ||--o{ CHI_TIET_DON_HANG : "thuộc"
    DON_DAT_HANG ||--o{ PHIEU_GIAO_HANG : "được giao"
    NOI_GIAO ||--o{ PHIEU_GIAO_HANG : "đến"
    NGUOI_GIAO ||--o{ PHIEU_GIAO_HANG : "thực hiện"
    NGUOI_NHAN ||--o{ PHIEU_GIAO_HANG : "nhận"

    DON_VI_KHACH {
        string MaDV PK "Mã đơn vị"
        string TenDV "Tên đơn vị"
        string DiaChi "Địa chỉ"
        string DienThoai "Số điện thoại"
    }

    NGUOI_DAT {
        string MaSoND PK "Mã số người đặt"
        string HoTenND "Họ tên người đặt"
        string MaDV FK "Mã đơn vị"
    }

    HANG {
        string MaHang PK "Mã hàng"
        string TenHang "Tên hàng"
        string DvTinh "Đơn vị tính"
        string MoTaHang "Mô tả hàng"
    }

    DON_DAT_HANG {
        string SoDH PK "Số đơn hàng"
        string NgayDat "Ngày đặt hàng"
        string MaDV FK "Mã đơn vị"
    }

    CHI_TIET_DON_HANG {
        string SoDH PK,FK "Số đơn hàng"
        string MaHang PK,FK "Mã hàng"
        int SoLuongDat "Số lượng đặt"
    }

    PHIEU_GIAO_HANG {
        string SoPG PK "Số phiếu giao"
        string NgayGiao "Ngày giao hàng"
        string SoDH FK "Số đơn hàng"
        string MaSoDDG FK "Mã nơi giao"
        string MaSoNG FK "Mã người giao"
        string MaSoNN FK "Mã người nhận"
        int SoLuongGiao "Số lượng giao"
        float DonGia "Đơn giá"
    }

    NOI_GIAO {
        string MaSoDDG PK "Mã địa điểm giao"
        string TenNoiGiao "Tên nơi giao"
    }

    NGUOI_GIAO {
        string MaSoNG PK "Mã người giao"
        string HoTenNG "Họ tên người giao"
    }

    NGUOI_NHAN {
        string MaSoNN PK "Mã người nhận"
        string HoTenNN "Họ tên người nhận"
    }
