# AYKA Site Deployment Check

Bu çalışma alanında aktif proje `/workspace/ayka-site` ve aktif Git branch `work` olarak görünüyor.

## Şu anki kritik durum

- Vercel tarafında hâlâ `617c83f` commit'i görünüyorsa, Vercel güncel dosyaları değil eski deploy kaynağını yayınlıyor.
- Bu çalışma alanında remote URL görünmüyor; yani buradan GitHub/Vercel'e otomatik push bağlantısı doğrulanamıyor.
- Güncel site dosyası `index.html`; Vercel config dosyası `vercel.json`.

## Vercel'de bağlantıyı düzeltme adımları

1. Vercel Dashboard'da ilgili projeyi aç: `aykapromo-ayka-site-387p`.
2. **Settings → Git** bölümüne gir.
3. **Connected Git Repository** alanında doğru GitHub reposunun bağlı olduğunu doğrula.
4. **Production Branch** alanında Vercel'in yayınlayacağı branch'i doğru seç:
   - Bu çalışma alanında branch adı: `work`
   - GitHub'da sadece `main` veya `master` varsa, bu değişiklikleri önce o branch'e taşı/push et.
5. **Deployments** bölümüne dön ve yeni deploy başlat.
6. Canlı sitede footer metnini kontrol et: `Sürüm: 2026-05-20-hotfix`.

## Hızlı doğrulama komutları

```bash
git branch --show-current
git log --oneline -n 3
git remote -v
npm run build
```

Eğer Vercel deploy ekranında görünen commit hâlâ `617c83f` ise, sorun kodda değil; Vercel yanlış repo/branch veya eski deploy kaynağına bağlıdır.
