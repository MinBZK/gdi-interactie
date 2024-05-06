# Algemeen
Dit is de GitHub repository van de MIDO/GDI werkgroep interactie. Deze werkgroep is verantwoordelijk voor de (door)ontwikkeling van de domeinarchitectuur interactie. Je vindt hier het ArchiMate architectuurmodel, dat hoort bij de uitwerking van het domein. Deze <a 
href="https://pgdi.nl/groups/view/7d10e3c4-540d-4b20-ac04-d4011a6a90dc/architectuurraad-en-architectuurwerkgroepen/files/72b0edd9-c505-4ff2-b672-2aa87f6b46b6">uitwerking</a> is tot 20 mei 2024 in review.

Het architectuurmodel is beschikbaar in verschillende vormen:

1. In de vorm van <a href="interactie.archimate">een bestand</a> voor het modelleertool Archi;
2. Als bestanden die kunnen worden ingelezen met de coArchi plugin van Archi;
3. Als <a href="https://minbzk.github.io/gdi-interactie">website</a> in de vorm van een HTML report uit Archi;
4. In pagina's en overzichten die met een script zijn geëxporteerd uit Archi om er op een vriendelijke manier doorheen te navigeren.</a> 

Er zijn <a href="https://github.com/MinBZK/gdi-gegevensuitwisseling/blob/master/instructies.md">instructies</a> beschikbaar voor het aanbrengen van wijzigingen en het installeren en configureren van Archi. Daarnaast is er een beschrijving van het gehanteerde <a href="https://github.com/MinBZK/gdi-gegevensuitwisseling/blob/master/metamodel.md">metamodel</a>. 

Bij de verschillende onderdelen van de architectuur wordt verwezen naar beschrijvingen, diagrammen, overzichten en detailoverzichten. Deze zijn allemaal geëxporteerd uit het architectuurmodelleertool Archi. De diagrammen zijn onderdeel van de standaard Archi HTML report. De overzichten, detailoverzichten en achterliggende detailpagina's zijn gegenereerd met een <a href="scripts/export HTML.ajs">script</a>.

# Samenvatting Architectuur Interactie
<!--
Inleiding: <a href="https://minbzk.github.io/gdi-toegang/content/elements/id-9704fa59cc7b4b5e9daa53f1b32ec98d.html">beschrijving</a>.

Veranderfactoren:
* Ontwikkelingen: <a href="https://minbzk.github.io/gdi-toegang/content/views/ontwikkelingen.html">overzicht</a>
* Beleid: <a href="https://minbzk.github.io/gdi-toegang/content/views/beleid.html">overzicht</a>
* Wet- en regelgeving: <a href="https://minbzk.github.io/gdi-toegang/content/views/wetten.html">overzicht</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/wettendetails.html">details</a>
* Knelpunten: <a href="https://minbzk.github.io/gdi-toegang/content/views/knelpunten.html">overzicht</a>
* Capabilities: <a href="https://minbzk.github.io/gdi-toegang/?view=id-0b1de22ff1b248798b095a178cf065f8">diagram</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/capabilities.html">overzicht</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/capabilitiesdetails.html">details</a>

Doelarchitectuur:
* Architectuurvisie: <a href="https://minbzk.github.io/gdi-toegang/content/elements/id-57896b8c4e854e7b92ed667986aa09ee.html">beschrijving</a>
* Architectuurprincipes: <a href="https://minbzk.github.io/gdi-toegang/?view=id-4e701366fd844120b700c114068bc91e">diagram</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/principes.html">overzicht</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/principesdetails.html">details</a>
* Gewenste voorzieningen: <a href="https://minbzk.github.io/gdi-toegang/?view=id-6b127e72ba554982a8ade48d06e2286c">diagram</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/gewenste%20voorzieningen.html">overzicht</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/gewenste%20voorzieningendetails.html">details</a>
* Veranderinitiatieven: <a href="https://minbzk.github.io/gdi-toegang/content/views/veranderinitiatieven.html">overzicht</a>

Bijlagen:
* Functies: <a href="https://minbzk.github.io/gdi-toegang/?view=id-e1cf58e0b07f4907bdce34ba561b9a18">diagram</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/bedrijfsfuncties.html">overzicht</a>
* Bedrijfsobjecten: <a href="https://minbzk.github.io/gdi-toegang/?view=id-efc531031d114860a309f6eeacdad289">diagram</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/bedrijfsobjecten.html">overzicht</a>
* Relatie tussen functies en bedrijfsobjecten: <a href="https://minbzk.github.io/gdi-toegang/?view=id-d24214a9135947e980983cea632143d2">diagram</a>
* Huidige voorzieningen: <a href="https://minbzk.github.io/gdi-toegang/?view=id-6b127e72ba554982a8ade48d06e2286c">diagram</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/huidige%20voorzieningen.html">overzicht</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/huidige%20voorzieningendetails.html">details</a>
* Standaarden: <a href="https://minbzk.github.io/gdi-toegang/?view=id-f14d78e817cf494cabe940d8c59f8a4e">diagram</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/standaarden.html">overzicht</a>, <a href="https://minbzk.github.io/gdi-toegang/content/views/standaardendetails.html">details</a>
* Begrippen: <a href="https://www.noraonline.nl/wiki/Begrippen_IAM">overzicht</a>
* Relatie van architectuurprincipes met ADO en NORA: <a href="https://minbzk.github.io/gdi-toegang/content/elements/id-2ce199487e094f099863995e07a7e605.html">overzicht</a>

Documenten:
* Samenvatting van de belangrijkste onderdelen in één pagina: <a href="https://minbzk.github.io/gdi-toegang/content/views/Domeinarchitectuur%20toegang.html">samenvatting</a>
* Bijlagen in één pagina: <a href="https://minbzk.github.io/gdi-toegang/content/views/Bijlagen%20domeinarchitectuur%20toegang.html">bijlagen</a>-->
