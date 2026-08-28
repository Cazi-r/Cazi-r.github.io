# cazi-r.github.io

Kişisel portfolyo sitesi — retro masaüstü arayüzü.

**Canlı:** https://cazi-r.github.io

## Yapı

Tek dosya: `index.html`. Harici bağımlılık yok (yalnızca Google Fonts).

| Bileşen | Açıklama |
|---|---|
| Arka plan | WebGL2 fragment shader, Bayer dither, 4 saniyelik döngü |
| Pencereler | Sürüklenebilir, küçültülüp kapatılabilir, hayalet iz animasyonlu |
| `projects/` | 17 projenin dosya yöneticisi görünümü, filtrelenebilir |
| `activity.mon` | Commit sayılarına göre süreç monitörü |
| `snake.exe` | Çalışan Snake oyunu, skor `localStorage`'da |
| `demo.player` | Video oynatıcı (kaynak eklenmeyi bekliyor) |
| Asistan | Animasyonlu ataç, tıklayınca cevap veriyor |
| Ses | Web Audio ile sentezlenen CRT cızırtısı |
| Dil | EN / TR, taskbar'dan değiştirilir |

## Video ekleme

`demo.player` penceresi kaynak bekliyor. Video dosyasını repo köküne koy ve
`index.html` içinde şu satırı bul:

```html
<video id="demoVideo" preload="metadata" playsinline ...></video>
```

`src` ekle:

```html
<video id="demoVideo" src="demo.mp4" preload="metadata" playsinline ...></video>
```

Kaynak tanımlanınca placeholder kaybolur, kontroller açılır, süre ve
çözünürlük durum çubuğuna otomatik yazılır.

## İçerik güncelleme

Projeler `index.html` içindeki `PROJECTS` dizisinde:

```js
{n:"Ad", d:"Türkçe açıklama", dEn:"English description",
 t:["Teknoloji"], c:387, open:false, org:"Kurum", live:null, tags:["dotnet"]}
```

`c` commit sayısı, `open` kaynağın açık olup olmadığı, `tags` filtre etiketleri.
