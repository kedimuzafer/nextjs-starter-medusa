# Medusa Next.js Frontend Geliştirme Rehberi

## Proje Yapısı

Frontend projemiz Next.js 14 App Router kullanıyor ve şu ana bileşenlerden oluşuyor:

```
src/
├── app/                   # App Router sayfaları
├── lib/                   # Utility fonksiyonları ve API client
├── modules/               # Ana UI bileşenleri
└── styles/               # Global stiller
```

## Hızlı Başlangıç için UI Geliştirmeleri

### 1. shadcn/ui Entegrasyonu

```bash
# shadcn kurulumu
npx shadcn@latest init

# Sık kullanılan bileşenleri ekleyin
npx shadcn@latest add button
npx shadcn@latest add card
npx shadcn@latest add dialog
```

### 2. Özelleştirilecek Ana Bileşenler

- `modules/layout/templates/nav/index.tsx` - Ana navigasyon
- `modules/products/components/product-preview/index.tsx` - Ürün kartları
- `modules/products/templates/product-info/index.tsx` - Ürün detay sayfası
- `modules/cart/templates/cart-modal/index.tsx` - Sepet modalı
- `modules/checkout/templates/checkout-form/index.tsx` - Ödeme formu

### 3. Tema Özelleştirme

1. `tailwind.config.js` dosyasını güncelleyin:
```js
module.exports = {
  // ... mevcut config
  theme: {
    extend: {
      colors: {
        // Marka renklerinizi ekleyin
        primary: { /* ... */ },
        secondary: { /* ... */ }
      }
    }
  }
}
```

2. `styles/globals.css` içinde CSS değişkenlerini güncelleyin

### 4. Responsive Tasarım İpuçları

- Tüm bileşenler Tailwind CSS ile stillendirilmiş
- Mobile-first yaklaşım kullanılıyor
- `sm:`, `md:`, `lg:` breakpointlerini kullanarak responsive düzenlemeler yapabilirsiniz

## Önemli Dosyalar ve Özelleştirmeler

1. Layout Değişiklikleri:
   - `app/[countryCode]/layout.tsx` - Ana layout
   - `modules/layout/templates/footer/index.tsx` - Footer

2. Ürün Listesi ve Detay:
   - `app/[countryCode]/products/page.tsx` - Ürün listesi
   - `app/[countryCode]/products/[handle]/page.tsx` - Ürün detay

3. Sepet ve Ödeme:
   - `modules/cart/components/` - Sepet bileşenleri
   - `modules/checkout/components/` - Ödeme bileşenleri

## Layout Bileşenleri Detayları

### Ana Layout Dosyaları
- `app/layout.tsx` - Root layout
- `app/[countryCode]/(main)/layout.tsx` - Ana sayfa layoutu
- `app/[countryCode]/(checkout)/layout.tsx` - Ödeme sayfası layoutu
- `app/[countryCode]/(main)/account/layout.tsx` - Hesap sayfası layoutu

### Layout Bileşenleri (`modules/layout/`)
1. Templates:
   - `templates/nav/index.tsx` - Ana navigasyon
   - `templates/footer/index.tsx` - Footer
   - `templates/index.tsx` - Layout wrapper

2. Components:
   - `components/cart-button/index.tsx` - Sepet butonu
   - `components/cart-dropdown/index.tsx` - Sepet dropdown menüsü
   - `components/country-select/index.tsx` - Ülke seçimi
   - `components/side-menu/index.tsx` - Mobil yan menü
   - `components/cart-mismatch-banner/index.tsx` - Sepet uyarı banner'ı
   - `components/medusa-cta/index.tsx` - Call-to-action bileşeni

### Hesap Layout
- `modules/account/templates/account-layout.tsx` - Hesap sayfaları layoutu

## Önerilen Geliştirmeler

1. UI/UX İyileştirmeleri:
   - shadcn bileşenlerini entegre edin
   - Animasyonlar için Framer Motion ekleyin
   - Loading state'leri için iskelet ekranlar ekleyin

2. SEO ve Performans:
   - Metadata'ları güncelleyin
   - Görsel optimizasyonları yapın
   - Next.js Image component'ini kullanın

3. Kullanıcı Deneyimi:
   - Toast bildirimleri ekleyin
   - Form validasyonlarını geliştirin
   - Error boundary'ler ekleyin

## Notlar

- Mevcut tema Tailwind CSS kullanıyor
- Server Components ve Client Components ayrımına dikkat edin
- Medusa API entegrasyonları `lib/data` klasöründe
- Tüm form işlemleri için react-hook-form kullanılıyor

## Başlarken

1. Önce shadcn/ui kurulumunu yapın
2. Global stilleri güncelleyin
3. Ana bileşenleri sırayla özelleştirin
4. Yeni özellikler ekleyin

Detaylı bilgi için [Medusa Docs](https://docs.medusajs.com) ve [Next.js Docs](https://nextjs.org/docs)'u inceleyebilirsiniz.
