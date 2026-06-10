# Tender systems RSS widget

Tento repozitář obsahuje jednoduchý HTML widget pro zobrazení novinek z RSS feedu:

- RSS: `https://www.tendersystems.cz/aktuality/feed`
- 1 sloupec novinek pod sebou
- název, české datum a zkrácený text bez obrázků
- 10 novinek na stránku
- stránkování

## Nasazení na GitHub Pages

1. Vytvořte nový veřejný repozitář.
2. Nahrajte do něj soubor `index.html`.
3. V repozitáři otevřete **Settings → Pages**.
4. V části **Build and deployment** nastavte:
   - **Source:** Deploy from a branch
   - **Branch:** main
   - **Folder:** /root
5. Uložte.
6. GitHub Pages vám vytvoří veřejnou URL ve tvaru:

```text
https://agillis24.github.io/ts_aktuality/
```

Pokud se vám zobrazuje 404, zkontrolujte ještě v repozitáři **Settings → Pages**, že je jako zdroj nastavená větev `main` a složka `/root`.

## Vložení do Weebly

Do prvku **Embed Code** ve Weebly vložte:

```html
<iframe
  id="ts-novinky-widget"
  src="https://agillis24.github.io/ts_aktuality/"
  title="Tender systems – novinky"
  width="100%"
  height="1200"
  frameborder="0"
  scrolling="no"
  style="width:100%; border:0; overflow:hidden; display:block;">
</iframe>

<script>
window.addEventListener('message', function(event) {
  if (!event.data || event.data.type !== 'tendersystems-widget-height') return;
  var iframe = document.getElementById('ts-novinky-widget');
  if (iframe) iframe.style.height = event.data.height + 'px';
});
</script>
```

## Úpravy

V souboru `index.html` můžete upravit:

- `RSS_URL`
- `PAGE_SIZE`
- barvy ve `<style>`
- texty tlačítek a nadpisů
