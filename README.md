Neymar Jr. (O Mágico) - Moderní webová prezentace

1. Úvod

Název projektu: Neymar Jr. - Webový profil
Popis tématu: Komplexní, vysoce optimalizovaná webová prezentace věnovaná kariéře, statistikám a magii fotbalisty Neymara Jr. Projekt demonstruje pokročilé znalosti moderních webových technologií, přístupnosti, SEO a optimalizace výkonu.
Autor: Matěj Jankech
Živý web: https://insanematej.github.io/Final_Work_Neymar.jr/

3. Použité technologie

HTML5 (Plně sémantické značkování)

CSS3 (Mobile First, CSS Variables, Flexbox, Grid, CSS animace a clip-path)

Vanilla JavaScript (ES6+) (DOM API, IntersectionObserver API pro lazy loading a scroll reveal)

Žádné frameworky: Vše tvořeno čistě (žádný Bootstrap, Tailwind, ani React).

IDE: Visual Studio Code

Verzovací systém: Git & GitHub

3. Adresářová struktura

Projekt je aktuálně pro maximální rychlost načítání složen v jednom optimalizovaném souboru (případně rozdělen takto):

neymar-projekt/
│
├── index.html       # Hlavní HTML dokument (včetně stylů a skriptů)
├── README.md        # Tato dokumentace
└── assets/          # Obrázky (načítané primárně přes URL)


4. Technický rozbor optimalizací

4.1 Výkon (Performance)

Teorie: Web obsahuje bohatou fotogalerii ve vysokém rozlišení. Aby se předešlo dlouhému načítání stránky (tzv. TTI - Time to Interactive), je implementován Lazy Loading. Obrázky se stahují až ve chvíli, kdy k nim uživatel fyzicky přiblíží scrollováním.
Code snippet (JS):

const imgObserver = new IntersectionObserver((entries, observer) => {
    entries.forEach(entry => {
        if (!entry.isIntersecting) return;
        const img = entry.target;
        img.src = img.getAttribute('data-src'); // Prohození placeholderu za reálná data
        img.onload = () => img.classList.add('loaded'); // Spuštění CSS animace po načtení
        observer.unobserve(img);
    });
}, { rootMargin: "0px 0px 50px 0px" });


4.2 SEO (Search Engine Optimization)

Teorie: Pro vysoké hodnocení vyhledávači využívám striktně sémantické tagy (<header>, <main>, <section>, <article>). V hlavičce je implementováno strukturované schéma JSON-LD pro typ objektu "Person".
Code snippet (HTML):

<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Neymar Jr.",
  "givenName": "Neymar",
  "familyName": "da Silva Santos Júnior",
  "jobTitle": "Profesionální fotbalista",
  "nationality": "Brazilská"
}
</script>


4.3 Přístupnost (Accessibility / a11y)

Teorie: Web splňuje standardy WCAG. Barevná paleta (zlatá #f59e0b na tmavém #0f172a pozadí) poskytuje obrovský kontrastní poměr. Stránku lze plně ovládat klávesnicí (Tabulátor), obsahuje skrytý odkaz "Přeskočit na hlavní obsah" a stavové atributy aria-expanded pro mobilní menu.
Code snippet (CSS & JS):

/* Jasný focus indikátor pro klávesnici (a11y) */
*:focus-visible {
    outline: 3px solid var(--color-accent);
    outline-offset: 4px;
    border-radius: 2px;
}


// Přepínání ARIA atributů pro čtečky obrazovek (NVDA, VoiceOver)
btnMenu.setAttribute('aria-expanded', !isExpanded);


4.4 Sociální sítě

Teorie: Aby odkaz na web sdílený na Facebooku nebo X (Twitteru) vypadal profesionálně, využívám protokoly Open Graph a Twitter Cards. To zajistí zobrazení velkého náhledového obrázku a správného titulku.
Code snippet (HTML):

<meta property="og:title" content="Neymar Jr. | O Mágico">
<meta property="og:image" content="https://images.alphacoders.com/132/1327049.jpeg">
<meta name="twitter:card" content="summary_large_image">


4.5 UI/UX (User Interface / Experience)

Teorie: Web je koncipován stylem Mobile First. Rozvržení používá moderní CSS moduly: Flexbox a CSS Grid. Design je oživen pokročilým využitím clip-path pro vytvoření dynamických zešikmených hran u sekce statistik.
Code snippet (CSS):

/* Dynamické zkosení hrany sekce pro sportovní vzhled */
.stats {
    clip-path: polygon(0 4%, 100% 0, 100% 96%, 0 100%); 
    margin: -2rem 0; 
}


4.6 AI Integrace (AI Deník)

Při návrhu a kódování webu byl využit LLM model jako asistent pro optimalizaci a zefektivnění vývoje.

Klíčové prompty a jejich přínos:

Prompt: "Vygeneruj mi JSON-LD schéma pro slavnou osobu, konkrétně fotbalistu Neymara."

Přínos: Rychle sestavená struktura strukturovaných dat plně validní podle schema.org.

Prompt: "Jaký je moderní a čistý Vanilla JS postup pro lazy-loading obrázků bez knihoven?"

Přínos: AI navrhla využití IntersectionObserver API místo zastaralého hlídání eventu window.onscroll, což rapidně zvedlo výpočetní výkon stránky.

Prompt: "Chci přidat přechody mezi sekcemi a dynamicky zkosit pozadí statistik jako na profi sportovním webu."

Přínos: AI vygenerovala CSS pravidlo clip-path a kód pro kaskádové odhalování prvků při scrollování (Scroll Reveal).

5. Instalace a spuštění

Kód stáhněte a otevřete ve složce projektu.

Stačí otevřít soubor index.html v libovolném moderním prohlížeči (Chrome, Firefox, Safari).

Pro vývoj doporučuji rozšíření Live Server ve VS Code.

6. Galerie

(Zde jsou screenshoty finálního webu)
