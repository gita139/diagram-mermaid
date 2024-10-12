```mermaid
graph TD
    subgraph Pelanggan
    A[Mulai] --> B[Pesan Produk]
    M[Terima Paket] --> N[Selesai]
    L[Hubungi Layanan Pelanggan] --> N
    end

    subgraph "Toko Online"
        subgraph "Sistem Pemesanan"
        C[Terima Pesanan] --> D[Proses Pesanan]
        end
        subgraph "Bagian Keuangan"
        E{Verifikasi Pembayaran}
        end
        subgraph "Layanan Pelanggan"
        K[Tangani Masalah]
        end
    end

    subgraph Gudang
        subgraph Penyimpanan
        F{Cek Ketersediaan}
        end
        subgraph Pengemasan
        G[Kemas Produk]
        end
    end

    subgraph Kurir
    H[Ambil Paket] --> I[Kirim Paket]
    end

    B --> C
    D --> E
    E -->|Berhasil| F
    E -->|Gagal| K
    F -->|Tersedia| G
    F -->|Tidak Tersedia| K
    G --> H
    I --> M
    M --> L

    %% Message Flows
    B -.-> C
    K -.-> L
    I -.-> M
