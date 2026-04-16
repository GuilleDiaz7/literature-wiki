# log.md — Append-Only Chronological Record

> This file records every agent action in chronological order.
> Entries are never deleted or edited. New entries are always appended.

---

## 2026-04-13 — Initial wiki build

**Action**: Initial wiki structure created from three raw sources.

**Sources ingested**:
1. Torné, Gonzalo. "'Albión', de Anna Hope: falsear el hoy." *El Periódico*, 9 March 2026.
2. Torné, Gonzalo. "'Los amores inconstantes', de Benjamin Constant: intermitencias." *El Periódico*, 9 February 2026.
3. Torné, Gonzalo. "'Física de la tristeza', de Gueorgui Gospodínov: pellizcos." *El Periódico*, 24 March 2026.

**Pages created**:

*Sources*:
- `sources/2026-03-09_albion-anna-hope.md`
- `sources/2026-02-09_amores-inconstantes-constant.md`
- `sources/2026-03-24_fisica-tristeza-gospodinov.md`

*Works*:
- `works/hope_albion.md`
- `works/constant_amores-inconstantes.md`
- `works/gospodinov_fisica-de-la-tristeza.md`

*Authors*:
- `authors/hope_anna.md`
- `authors/constant_benjamin.md`
- `authors/gospodinov_gueorgui.md`

*Critics*:
- `critics/torne_gonzalo.md`

*Themes*:
- `themes/literatura-decorativa.md`
- `themes/intermitencias-del-corazon.md`
- `themes/realismo-magico.md`

*Infrastructure*:
- `index.md` — updated from empty template
- `log.md` — created (this file)

**Contradictions flagged**: None (only one critic so far; no cross-source contradictions possible yet).

**Outstanding gaps flagged** (for future ingestion):
- Author pages needed: Jane Austen, Iris Murdoch, E.M. Forster, Charles Dickens, Joseph Conrad, Blaise Pascal, Honoré de Balzac, Marcel Proust, Stendhal, Virginia Woolf.
- Work pages needed: Austen's *Emma*, *Mansfield Park*, *Persuasion*; Woolf's *Orlando*; Gospodínov's *El manual del tiempo*.
- Period pages needed: Victorian Literature, French Romanticism, Contemporary Fiction.
- All current content derives from a single critic (Gonzalo Torné, *El Periódico*). The wiki requires additional critical voices before any position can be treated as representative.

---

## 2026-04-13 — Second build: 14 new sources ingested; translator schema added

**Action**: Ingested 14 further reviews by Gonzalo Torné from *El Periódico* (2024–2025); added translator schema to AGENTS.md; updated all entity pages, themes, critics, and index accordingly.

**AGENTS.md changes**:
- Added `translators/` to the directory structure (§2).
- Added `translator:` field to the Work Page frontmatter template (§3.1).
- Added §3.10 Translator Page template with When-to-create criteria.
- Added workflow step 6 for translator handling during source ingestion (§4.1).
- Added translator conventions note (§6).

**Sources ingested**:
1. Torné, Gonzalo. "'Los vulnerables', de Sigrid Nunez: los matices de la delicadeza." *El Periódico*, 1 October 2024.
2. Torné, Gonzalo. "'La impostura', de Zadie Smith: volverás al victorianismo." *El Periódico*, 14 November 2024.
3. Torné, Gonzalo. "'En una habitación ajena', de Damon Galgut: viajar, llorar, enamorarse." *El Periódico*, 2 December 2024.
4. Torné, Gonzalo. "'Imposible decir adiós', de Han Kang: lealtades y masacres." *El Periódico*, 13 January 2025.
5. Torné, Gonzalo. "'La estatua', de Günter Grass: un mensaje cifrado." *El Periódico*, 5 February 2025.
6. Torné, Gonzalo. "'Tierra de empusas', de Olga Tokarczuk: borrados electivos." *El Periódico*, 26 March 2025.
7. Torné, Gonzalo. "'Desfile', de Rachel Cusk: modelos de sabotaje." *El Periódico*, 6 April 2025.
8. Torné, Gonzalo. "'Proust, novela familiar', de Laure Murat: la salvación." *El Periódico*, 12 May 2025.
9. Torné, Gonzalo. "'Un puñado de polvo', de Evelyn Waugh: apatía y asco en la campiña inglesa." *El Periódico*, 4 June 2025.
10. Torné, Gonzalo. "'Andar', de Thomas Bernhard: laberintos del pensar." *El Periódico*, 28 June 2025.
11. Torné, Gonzalo. "'Tiempo profundo', de Ana Gorría: una chica y su álbum de fotos." *El Periódico*, 31 July 2025.
12. Torné, Gonzalo. "'Radio Benjamin', de Walter Benjamin, ilustrado por Judy Kaufmann: iconos." *El Periódico*, 1 October 2025.
13. Torné, Gonzalo. "'El Vado de los Zorros', de Anna Starobinets: iconos." *El Periódico*, 12 November 2025.
14. Torné, Gonzalo. "'El Mago', de John Fowles: los peligros de abandonarse a una voluntad superior." *El Periódico*, 31 December 2025.

**Pages created**:

*Sources* (14 new):
- `sources/2024-10-01_los-vulnerables-nunez.md`
- `sources/2024-11-14_la-impostura-smith.md`
- `sources/2024-12-02_habitacion-ajena-galgut.md`
- `sources/2025-01-13_imposible-decir-adios-kang.md`
- `sources/2025-02-05_la-estatua-grass.md`
- `sources/2025-03-26_tierra-empusas-tokarczuk.md`
- `sources/2025-04-06_desfile-cusk.md`
- `sources/2025-05-12_proust-novela-familiar-murat.md`
- `sources/2025-06-04_punado-polvo-waugh.md`
- `sources/2025-06-28_andar-bernhard.md`
- `sources/2025-07-31_tiempo-profundo-gorria.md`
- `sources/2025-10-01_radio-benjamin.md`
- `sources/2025-11-12_el-vado-zorros-starobinets.md`
- `sources/2025-12-31_el-mago-fowles.md`

*Works* (14 new):
- `works/nunez_los-vulnerables.md`
- `works/smith_la-impostura.md`
- `works/galgut_en-una-habitacion-ajena.md`
- `works/kang_imposible-decir-adios.md`
- `works/grass_la-estatua.md`
- `works/tokarczuk_tierra-de-empusas.md`
- `works/cusk_desfile.md`
- `works/murat_proust-novela-familiar.md`
- `works/waugh_punado-de-polvo.md`
- `works/bernhard_andar.md`
- `works/gorria_tiempo-profundo.md`
- `works/benjamin_radio-benjamin.md`
- `works/starobinets_el-vado-de-los-zorros.md`
- `works/fowles_el-mago.md`

*Authors* (14 new):
- `authors/nunez_sigrid.md`
- `authors/smith_zadie.md`
- `authors/galgut_damon.md`
- `authors/kang_han.md`
- `authors/grass_gunter.md`
- `authors/tokarczuk_olga.md`
- `authors/cusk_rachel.md`
- `authors/murat_laure.md`
- `authors/waugh_evelyn.md`
- `authors/bernhard_thomas.md`
- `authors/gorria_ana.md`
- `authors/benjamin_walter.md`
- `authors/starobinets_anna.md`
- `authors/fowles_john.md`

*Themes* (6 new):
- `themes/vulnerabilidad-y-delicadeza.md`
- `themes/novela-victoriana-contemporanea.md`
- `themes/literatura-de-viajes.md`
- `themes/violencia-historica-trauma.md`
- `themes/creacion-femenina.md`
- `themes/memoria-familiar.md`

*Translators* (1 new):
- `translators/saenz_miguel.md`

**Pages updated**:
- `agents.md` — translator schema added
- `critics/torne_gonzalo.md` — expanded to 17 sources with 7 key arguments
- `themes/realismo-magico.md` — added Starobinets counterpoint; contradiction flagged
- `index.md` — fully rebuilt with all 62 pages and 17 sources

**Contradictions flagged**:
- `themes/realismo-magico.md`: Torné uses the magical realism label analogically for Gospodínov but rejects it definitionally for Starobinets. Both uses are by the same critic; the definitional argument clarifies the analogy. No external contradiction — internal nuance mapped.
- `themes/creacion-femenina.md`: Torné evaluates Cusk positively and Tokarczuk with reservations on adjacent feminist themes. Mapped as an open critical question: what distinguishes successful feminist fiction from programmatic feminist fiction?
- `works/tokarczuk_tierra-de-empusas.md`: the novel's feminist denunciation of women's erasure is itself argued to practise "elective erasures" of women in literature. Torné's position mapped; no counter-reading yet.

**Outstanding gaps flagged** (updated):
- Author pages still needed: Jane Austen, Iris Murdoch, E.M. Forster, Charles Dickens, Joseph Conrad, Blaise Pascal, Honoré de Balzac, Marcel Proust, Stendhal, Virginia Woolf, Thomas Mann, Robert Musil, Ali Smith, Emily Dickinson, Julio Cortázar, Jorge Luis Borges, F. Scott Fitzgerald, J.D. Salinger, Thomas Pynchon, Umberto Eco, Javier Marías, Imre Kertész, Jon Fosse, George Eliot, Brontë sisters, Gustave Flaubert, Tolstoy, Dostoyevsky, Galdós, Clarín.
- Work pages still needed: Bernhard's masterworks (*Trastorno*, *La calera*, *Corrección*, *El malogrado*, *Maestros antiguos*); Mann's *La montaña mágica*; Woolf's *Orlando*; James's *The Turn of the Screw*; Proust's *Recherche*.
- Period pages still needed: Victorian Literature, French Romanticism, Contemporary Fiction, Austrian Post-War Fiction, Weimar Republic.
- Concept pages still needed: Anti-biographical formalism, negative charisma.
- Translator pages still needed: Sáenz's specific translated titles (unverified); other translators with critical discussion.
- All current content still derives from a single critic (Gonzalo Torné). Second critical voice urgently needed for any position to be treated as representative.

---

## 2026-04-14 — Third build: 27 new sources ingested; 4 new critics; expanded corpus 2019–2026

**Action**: Automated scheduled task. Ingested all 27 remaining unprocessed raw files from `raw/`. Added four new critical voices to the wiki (Mora, Serra Bradford, García Nieto, Marías). Significantly expanded author, work, and theme coverage. Total wiki now 144 pages, 44 sources.

**New critics added** (major gap addressed):
1. Vicente Luis Mora — Spanish critic/novelist; structural-formal analysis; "novelas de la teoría"
2. Matías Serra Bradford — Argentine, *Clarín*; first Latin American publication in the wiki
3. Rebeca García Nieto — Spanish; ethical/existential reading; Central/Eastern European fiction
4. Miguel Marías — Spanish film and literary critic; canon-building and recovery

**Sources ingested (27 new)**:

*Torné, Gonzalo (22 reviews/essays):*
1. "Acerca del robo de historias, de Gospodínov." 18 March 2024.
2. "Bruja Luna, Rey Araña, de Marlon James." 31 December 2023.
3. "Cartas I, de H.P. Lovecraft." 26 March 2023.
4. "Ciudad Victoria, de Salman Rushdie." 12 February 2023.
5. "Diario de sueños, de H.P. Lovecraft." 20 May 2024.
6. "El movimiento del cuerpo a través del espacio, de Shriver." 15 July 2023.
7. "Encontrar la chica, de Andre Dubus III." 3 April 2024.
8. "Historia y aventuras de un átomo, de Smollett." 16 June 2024.
9. "Hombres fatales, de Elisenda Julibert." 2 November 2022.
10. "La bóveda de voces, de Ramón Andrés." 6 December 2022.
11. "Fechas exactas de personas amadas, de Mario Amadas." 17 September 2023.
12. "Mañana y tarde, de Jon Fosse." 5 November 2023.
13. "Salir a robar caballos, de Per Petterson." 31 December 2022.
14. "Sé mía, de Richard Ford." 30 June 2024.
15. "El occidente secuestrado, de Kundera." 13 March 2023.
16. "Viaje a Grecia, de Mario Praz." 22 July 2024.
17. "Dos andando juntos" (essay). Undated.
18. "Correspondencia Flaubert-Baudelaire." 4 June 2023.
19. "Calvino (centenary essay)." September 2023.
20. "Javier Marías (obituary)." 12 September 2022.
21. "Miradores del tiempo" (on Donoso's Jane Austen essay). 4 February 2023.
22. "'La ciudad y sus muros inciertos', de Haruki Murakami." 15 April 2024.

*Other critics (5 sources):*
23. Mora, Vicente Luis. "El tratado de Sara Barquinero." 5 April 2026.
24. Serra Bradford, Matías. "Ribeyro en Buenos Aires." 3 April 2026. (*Clarín*)
25. García Nieto, Rebeca. "El jardinero y la muerte, de Gospodínov." September 2025.
26. Marías, Miguel. Prologue to *Juego de espera* (Powell). 13 April 2026.
27. Eco, Umberto. "El culto imperfecto" (essay excerpt, 1987; blog repost October 2019).

**Pages created**:

*Works (23 new)*: gospodinov_acerca-del-robo, james_bruja-luna-rey-arana, fosse_manana-tarde, petterson_salir-robar-caballos, rushdie_ciudad-victoria, kundera_occidente-secuestrado, murakami_ciudad-muros, lovecraft_cartas-i, lovecraft_diario-suenos, shriver_movimiento-cuerpo, dubus_encontrar-chica, smollett_historia-atomo, julibert_hombres-fatales, andres_boveda-voces, amadas_fechas-exactas, ford_se-mia, praz_viaje-grecia, barquinero_chica-mas-lista, ribeyro_tentacion-del-fracaso, gospodinov_jardinero-muerte, powell_juego-de-espera, flaubert-baudelaire_correspondencia, donoso_jane-austen-pensamiento.

*Authors (24 new)*: james_marlon, lovecraft_hp, rushdie_salman, shriver_lionel, fosse_jon, petterson_per, kundera_milan, murakami_haruki, marias_javier, calvino_italo, eco_umberto, ribeyro_julio-ramon, julibert_elisenda, andres_ramon, amadas_mario, ford_richard, praz_mario, barquinero_sara, dubus_andre-iii, smollett_tobias, donoso_jose, powell_anthony, flaubert_gustave, baudelaire_charles.

*Critics (4 new)*: mora_vicente-luis, serra-bradford_matias, garcia-nieto_rebeca, marias_miguel.

*Themes (4 new)*: ensayo-hibrido, mujer-fatal, lo-extrano, satira-social.

**Pages updated**:
- `critics/torne_gonzalo.md` — expanded to 40+ sources; 8 new key arguments; full works-discussed list
- `authors/gospodinov_gueorgui.md` — now 3 works, 2 critics
- `themes/realismo-magico.md` — added Rushdie and Murakami; Torné's three-tier hierarchy mapped
- `themes/literatura-de-viajes.md` — added Praz and Amadas
- `index.md` — rebuilt to 144 pages, 44 sources

**Contradictions flagged**:
- `works/murakami_ciudad-muros.md`: Torné's magical realism hierarchy is a personal position; general critical reception treats Murakami as a distinct tradition.

**Outstanding gaps** (updated):
- No translator page yet for María Vútova (Gospodínov, high priority) or David Paradela López
- Javier Marías and Calvino have author pages but no individual work pages
- Period pages remain at zero
- Single-source author assessments (most new additions) should be treated as provisional until second critical voice is ingested

---

## 2026-04-14 — Ingest: Bonilla, "Herralde" (2022)

**Action**: Ingested Juan Bonilla's essay on Jorge Herralde and Anagrama (*Jot Down*, 16 April 2022).

**Source created**:
- `sources/2022-04-16_herralde-bonilla.md`

**Pages updated**:
- `publishers/anagrama.md` — Editorial Profile section fully rewritten from sourced material: founding date confirmed (1968), first book (*L'ofici de viure*, Pavese), catalog phases (political essays → Cuadernos → Informal → Panorama de Narrativas → Biblioteca Nabokov), cover uniformity as identity strategy, Herralde's editorial character. Bonilla's key claims and quotations recorded.

**Notes**: First non-review, non-Torné source ingested. First source touching the publishers/ directory.

---

## 2026-04-15 — Ingest: cinco fuentes nuevas de Juan Bonilla (*Jot Down*)

**Acción**: Ingestión de las cinco primeras fuentes no procesadas de `raw/`. Todas firmadas por Juan Bonilla en *Jot Down* (2024–2025). Primer ingest íntegramente en español.

**Fuentes creadas**:
1. `sources/2025-07-15_historia-provincial-infamia-bonilla.md` — Reseña de *Historia provincial de la infamia* (David Monthiel), *Jot Down*, julio 2025.
2. `sources/2024-06-25_manos-trapo-prieto-bonilla.md` — Reseña de *Manos de trapo* (María Regla Prieto), *Jot Down*, junio 2024.
3. `sources/2024-11-05_recuerdos-tiempo-viejo-bonilla.md` — Ensayo sobre *Recuerdos del tiempo viejo* (José Zorrilla), *Jot Down*, noviembre 2024.
4. `sources/2024-07-23_the-best-garci-bonilla.md` — Reseña de *The Best?* (José Luis Garci), *Jot Down*, julio 2024.
5. `sources/2025-06-04_linares-poulidor-bonilla.md` — Artículo sobre la polémica Abelardo Linares / Chaves Nogales, *Jot Down*, junio 2025.

**Páginas de obras creadas** (5 nuevas):
- `works/monthiel_historia-provincial-infamia.md` — Monthiel, ficción biográfica flamenca, Algaida 2021, Premio Ciudad de Irún.
- `works/prieto_manos-de-trapo.md` — Prieto, novela, Renacimiento 2024, finalista Premio Nadal.
- `works/zorrilla_recuerdos-tiempo-viejo.md` — Zorrilla, memorias por entregas (1879–1880); última ed. Debate 2001.
- `works/garci_the-best.md` — Garci, ensayo cinematográfico, Notorious 2024.
- `works/chaves-nogales_diarios-sgm.md` — Chaves Nogales, crónica periodística, El Paseo 2025.

**Páginas de autores creadas** (5 nuevas):
- `authors/monthiel_david.md`
- `authors/prieto_maria-regla.md`
- `authors/zorrilla_jose.md`
- `authors/garci_jose-luis.md`
- `authors/chaves-nogales_manuel.md`

**Páginas de críticos creadas** (1 nueva):
- `critics/bonilla_juan.md` — 6 fuentes en el wiki; crítica impresionista; lector agradecido; desconfianza ante el canon democrático.

**Páginas de editoriales creadas** (3 nuevas):
- `publishers/algaida.md`
- `publishers/renacimiento.md`
- `publishers/notorious.md`

**Páginas de editoriales actualizadas**:
- `publishers/el-paseo.md` — añadido *Diarios de la SGM* de Chaves Nogales como segunda obra; incorporada información de la polémica Linares.

**Correcciones aplicadas en esta sesión** (anteriores al ingest de hoy):
- `works/powell_juego-de-espera.md` — Reescrito íntegramente: era contenido fabricado sobre Anthony Powell / *A Dance to the Music of Time*. Corregido a Michael Powell (director de cine), *A Waiting Game* (1975), Irlanda, guerra civil, familia Donohue.
- `works/dubus_encontrar-chica.md` — Corregido: autor era Dubus III (hijo); debe ser Andre Dubus (padre, 1936–1999). Título corregido a *Encontrar a una chica en América*.
- `authors/powell_anthony.md` — Eliminado (contenido fabricado).
- `authors/dubus_andre-iii.md` — Eliminado (persona incorrecta).
- `authors/powell_michael.md` — Creado (director de cine irlandés).
- `authors/dubus_andre.md` — Creado (padre, 1936–1999).

**Cambios de esquema en esta sesión**:
- `agents.md` — Añadidos directorios `publishers/` y `genres/` a la estructura; campo `original_title` al esquema de obras; plantilla de página de editorial (§3.11); comprobaciones de lint para translator y publisher_url faltantes (§4.3).
- `works/*.md` — Añadidos campos `publisher_url`, `publisher`, `original_title` a los 40+ archivos de obras.
- Idioma: a partir de este ingest, todo el contenido nuevo del wiki se escribe en español. Los originales en inglés o español no se traducen.

**Contradicciones registradas**: Ninguna nueva.

**Lagunas detectadas** (actualizadas):
- `index.md` y `log.md` aún en inglés (pendiente de reescribir en español).
- 6 obras aún con `translator: "not specified"`.
- 13 obras con `original_title: "[not specified in source]"`.
- Ninguna página de períodos literarios ni de recepciones críticas todavía.

---

## 2026-04-15 — Ingest: diez fuentes nuevas (segunda tanda)

**Acción**: Ingestión de las diez siguientes fuentes no procesadas de `raw/` (orden alfabético). Todas en español conforme a la norma de idioma establecida.

**Fuentes creadas** (9 archivos — las dos partes del ensayo sobre Borges se consolidan en una sola entrada):

1. `sources/2021-05-06_donde-esta-gracia-bonilla.md` — Bonilla, ensayo sobre bibliomanía, *Jot Down*, mayo 2021.
2. `sources/2021-10-30_como-no-antologia-bonilla.md` — Bonilla, crítica de la antología Jull Costa (Penguin), *The Objective*, octubre 2021.
3. `sources/2022-11-06_borges-sendero-bonilla.md` — Bonilla, ensayo en dos partes sobre Borges y el diario de Bioy Casares, *Jot Down*, noviembre 2022.
4. `sources/2024-06-18_arroyo-stephens-viento-bonilla.md` — Bonilla, reseña de *De donde viene el viento* (Arroyo-Stephens), *Jot Down*, junio 2024.
5. `sources/2024-09-24_duelo-sin-brujula-bonilla.md` — Bonilla, reseña de *Duelo sin brújula* (López Mercader), *Jot Down*, septiembre 2024.
6. `sources/2025-06-10_contra-obras-completas-bonilla.md` — Bonilla, ensayo contra las obras completas, *Jot Down*, junio 2025.
7. `sources/2025-07-01_azorin-fuster-bonilla.md` — Bonilla, reseña de la biografía de Azorín por Fuster, *Jot Down*, julio 2025.
8. `sources/2026-02-20_owens-madre-trabajadora-rodriguez.md` — Aloma Rodríguez, reseña de *Una madre trabajadora* (Owens), *Letras Libres*, febrero 2026.
9. `sources/2026-03-24_conget-adios-bonilla.md` — Bonilla, sobre *Adiós* de Conget, *Jot Down*, marzo 2026.

**Páginas de obras creadas** (7 nuevas):
- `works/fuster_azorin-biografia.md` — Fuster, biografía de Azorín, 2025.
- `works/bioy-casares_borges.md` — Bioy Casares, diario póstumo sobre Borges (c. 1.600 pp.).
- `works/conget_adios.md` — Conget, novela final, Pre-Textos 2026.
- `works/arroyo-stephens_de-donde-viene-el-viento.md` — Arroyo-Stephens, textos póstumos.
- `works/owens_una-madre-trabajadora.md` — Owens, *A Working Mother* (1994), trad. Blanca Gago, Muñeca Infinita.
- `works/lopez-mercader_duelo-sin-brujula.md` — López Mercader, testimonio, Reino de Redonda 2024 (último libro del sello).
- `works/jull-costa_relatos-espanoles.md` — Jull Costa (ed.), antología Penguin 2021, demolida por Bonilla.

**Páginas de autores creadas** (8 nuevas):
- `authors/azorin.md` — José Martínez Ruiz, 1873–1967, Generación del 98.
- `authors/borges_jorge-luis.md` — argentino, 1899–1986, cuentista y poeta.
- `authors/bioy-casares_adolfo.md` — argentino, 1914–1999, *La invención de Morel*.
- `authors/conget_jose-maria.md` — español, ca. 1955, narrador sistemáticamente ignorado.
- `authors/arroyo-stephens_manuel.md` — español, 1939–2014, fundador Turner, prosista extraordinario.
- `authors/owens_agnes.md` — escocesa, 1926–2014, escritora tardía y obrera.
- `authors/lopez-mercader_carme.md` — española, pareja de Marías, gestora de Reino de Redonda.

**Páginas de críticos creadas** (1 nueva):
- `critics/rodriguez_aloma.md` — Aloma Rodríguez, *Letras Libres*; primera fuente de esa publicación en el wiki.

**Páginas de traductores creadas** (2 nuevas):
- `translators/jull-costa_margaret.md` — traductora británica (español/portugués→inglés); compiladora cuestionada.
- `translators/gago_blanca.md` — traductora española (inglés→español); *Una madre trabajadora*.

**Páginas de editoriales creadas** (3 nuevas):
- `publishers/pre-textos.md` — Valencia, fund. 1976; sello de Conget.
- `publishers/muneca-infinita.md` — editorial española independiente; *Una madre trabajadora*.
- `publishers/turner.md` — Madrid, fund. ca. 1970s; Arroyo-Stephens; facsímiles y exiliados.

**Páginas actualizadas**:
- `critics/bonilla_juan.md` — ampliado a 14 fuentes y 7 argumentos principales (añadidos: antimonumentalismo, bibliomanía, Borges oblicuo, canon alternativo, defensa de Conget).
- `publishers/reino-de-redonda.md` — añadido cierre (2024), *Duelo sin brújula* como último libro, catálogo destacado según Bonilla.
- `authors/marias_javier.md` — añadida sección sobre Reino de Redonda y datos personales documentados en *Duelo sin brújula*.

**Nueva crítica ingresada**: Aloma Rodríguez (*Letras Libres*) — primera fuente de esa publicación mexicana en el wiki.

**Contradicciones registradas**: Ninguna nueva.

**Lagunas detectadas** (actualizadas):
- Cansinos Assens mencionado varias veces por Bonilla como figura clave; candidato a página de autor.
- Gonzalo Suárez mencionado por Bonilla como su novelista favorito de los cincuenta; candidato a página de autor.
- Francisco Ayala: ausencia señalada por Bonilla en la antología; candidato a página de autor.
- Jhumpa Lahiri y John Freeman: citados por Bonilla como antólogos ejemplares; sin páginas en el wiki.
- La bibliomanía como tema/concepto: documentada en fuente pero sin página propia.
- Azorín sin página de obra propia (solo la biografía de Fuster está en el wiki; ninguna obra suya directa).
