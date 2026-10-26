# MicrobIA

El laboratorio de microbiología agropecuaria en tu navegador. Aplicación web de un solo fichero.

**Usar la app:** https://fborrasumh.github.io/microbia/

**Idiomas:** español (por defecto), inglés y portugués; selector en la barra superior (o `?lang=en` / `?lang=pt` en la URL).

## Qué hace

Sigue el sílabo de Microbiología (código 0811BM2UB-AJ2025, nivel 2, Carrera de Agropecuaria, PAO 2026 B) de la Universidad Politécnica Estatal del Carchi: caracterizar microorganismos benéficos y patógenos de los sistemas de producción agropecuaria. Todo funciona sin clave de IA salvo donde se indica. Cada estudiante escribe un código o alias y recibe sus propias muestras, datos y aislados; con el mismo código se reproducen los mismos ejercicios.

- **Microscopio: tinción de Gram.** Frotis, cristal violeta, lugol, decoloración (0-60 s), safranina y edad del cultivo. El campo a 1000× se dibuja según un modelo de la tinción, de modo que los errores (sin fijar, sin lugol, decoloración corta o excesiva, sin contratinción, cultivo viejo) cambian lo que se ve. El estudiante informa del Gram, la forma y la agrupación; el código lo corrige y explica qué falló en el protocolo.
- **Laboratorio de cálculos.** Ocho tipos de problema con datos distintos por estudiante: medio deshidratado, agar al % (p/v), solución madre (C₁V₁ = C₂V₂), valor D y tiempo de esterilización hasta 10⁻⁶, valor z, tiempo de generación, UFC por gramo y cámara de Neubauer. El código calcula la solución y reconoce los errores típicos (mL por L, logaritmo natural, olvidar el volumen o el factor de dilución…) y los explica. Admite coma decimal y notación científica.
- **Recuento.** Cinco placas de diluciones seriadas (10⁻³ a 10⁻⁷) con recuentos simulados por Poisson a partir de un valor real: hay que elegir una placa de 30 a 300 colonias y calcular las UFC/g. Cámara de Neubauer dibujada para contar a mano cinco cuadros medianos.
- **Identificación.** 25 pruebas (Gram, esporas, catalasa, oxidasa, fermentaciones, indol, citrato, ureasa, movilidad, H₂S, nitrato, aerobiosis y anaerobiosis, pigmentos, pudrición en papa, TZC, Ashby, nodulación, coagulasa, CAMP, hemólisis, lecitinasa y geosmina) y 18 bacterias de importancia agropecuaria (*Pectobacterium*, *Ralstonia*, *Xanthomonas*, *Rhizobium*, *Azotobacter*, *Pseudomonas fluorescens*, *Bacillus*, *Clostridium*, *Staphylococcus aureus*, *Streptococcus agalactiae*, *Listeria*, *Lactiplantibacillus*, *Streptomyces*, enterobacterias…). Cada prueba cuesta «fichas»; el código mantiene los candidatos compatibles, sugiere la prueba más informativa y, ante una propuesta errónea, dice qué resultados la contradicen.
- **Casos del campo.** Seis casos de aprendizaje basado en problemas (pudrición blanda de la papa, marchitez bacteriana del tomate, mastitis contagiosa, agua del bebedero, fréjol sin nódulos efectivos, ensilaje y listeriosis) con decisiones paso a paso, pistas graduadas y un tutor socrático con IA.
- **Simulacro.** Test de 20 preguntas barajadas por estudiante a partir de un banco de 34, corregido con la clave; muestra aciertos por tema, no una nota. Cinco preguntas de desarrollo con revisión de conceptos sin IA y feedback formativo con IA.
- **Tarjetas, Lecturas y Progreso.** 33 tarjetas con repetición espaciada (cajas de Leitner); lectura crítica de artículos (investigación formativa del sílabo) a partir de un texto pegado o un PDF/Word; progreso por módulo y tema y cuaderno de laboratorio exportable a Word, CSV y JSON (importable).

## Cómo se usa la IA

Con la propia clave de OpenAI, Google Gemini o Anthropic Claude. La clave se guarda solo en el navegador. No hace falta servidor. La IA se usa solo en tres funciones: el feedback de las preguntas de desarrollo, el tutor de los casos y la guía de lectura crítica. No calcula, no corrige el test ni pone notas.

- Las citas que la IA atribuye a la respuesta del estudiante o al artículo se comprueban por código y se marcan con ⚠ si no aparecen literalmente; las cifras que no están en el artículo se avisan.
- Si la IA escribe una calificación, el código elimina la frase.
- El tutor no recibe la solución del caso y el código elimina las frases que nombran el microorganismo causante o la opción correcta.

## Privacidad

Todo se procesa y se guarda en el navegador (IndexedDB): progreso, respuestas y la clave de IA. Solo sale texto hacia el proveedor de IA si se usan sus funciones, con correos, documentos de identidad y teléfonos enmascarados y tras un aviso previo con una muestra de lo que sale. El JSON exportado no contiene la clave. Se recomienda usar un alias como código, no el nombre ni la cédula.

## Límites

- Es material de repaso elaborado a partir del sílabo: puede contener errores u omisiones. Mandan la profesora, el sílabo y los protocolos del laboratorio.
- La tinción de Gram, las placas y la cámara de Neubauer son **modelos didácticos**, no imágenes reales.
- Los perfiles bioquímicos son los típicos de manual, simplificados; las reacciones variables según cepa se resuelven al azar para cada aislado. Una identificación real a nivel de especie necesita más pruebas (galerías comerciales, MALDI-TOF o secuenciación del ARNr 16S).
- Las referencias normativas del agua se limitan a la guía de la OMS (E. coli no detectable en 100 mL de agua de consumo); cada país tiene su propia normativa.
- La revisión de conceptos sin IA busca palabras clave: orienta, pero no valora el razonamiento.
- El filtro del tutor es una lista de términos: puede dejar pasar una formulación inesperada.

Probado con IA simulada de los tres proveedores (incluida una IA que inventa citas, cuela una nota y chiva la solución), en español, inglés y portugués, en escritorio y móvil. Los generadores de problemas se comprobaron en Node con 2400 variantes y oráculos independientes, y la identificación con 400 aislados (el organismo real siempre queda como candidato y ningún par es indistinguible con todas las pruebas). **No se ha probado con una clave de API real.**

## Autoría

Fernando Borrás Rocher (Universidad Miguel Hernández de Elche) y Nataly Tatiana Coronel Montesdeoca (Universidad Politécnica Estatal del Carchi).

Sigue el sílabo de Microbiología (0811BM2UB-AJ2025, nivel 2, Carrera de Agropecuaria, PAO 2026 B) de la Universidad Politécnica Estatal del Carchi, cuya profesora responsable es Nataly Tatiana Coronel Montesdeoca.

ORCID: Fernando Borrás Rocher [0000-0002-5519-4573](https://orcid.org/0000-0002-5519-4573) · Nataly Tatiana Coronel Montesdeoca [0009-0008-6478-7339](https://orcid.org/0009-0008-6478-7339)

## Cómo citar

Borrás Rocher, F. y Coronel Montesdeoca, N. T. (2026). *MicrobIA* (v1.0.0) [Software].

## Licencia

MIT. Véase [LICENSE](LICENSE).
