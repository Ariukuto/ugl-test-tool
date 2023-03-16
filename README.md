# UGL Test Tool

## Beschreibung
Dieses Webtool wurde von mir entwickelt um Dateien des UGL Standards auslesen zu können.  
Im Gegensatz zu anderen Tools, funktioniert es auch bei fehlerhaften Dateien.  
Dies ermöglicht es, von Software erstellte UGL Dateien auf ihre Richtigkeit zu überprüfen und bei Fehlern,   
genau herauszufinden, woran der Fehler liegt, bzw. wo dieser aufgetreten ist.

## Aktuell unterstützte Satzarten
- KOP
- ADR
- POA
- POZ
- POT
- END

## Get Started
````js
const ugl = new uglTool({
	encoding: 'CP437',
	kopfdatenfelder: kopfdatenfelder,
	adressdatenfelder: adressdatenfelder,
	positionsdatenfelder: positionsdatenfelder,
	pozFelder: pozFelder,
	potFelder: potFelder,
	endFelder: endFelder,
	anfrageArten: anfrageArten,
});
````

## Konstanten

````js
const kopfdatenfelder = [
	{ label: "Satzart", bis: 3 },
	{ label: "KundenNr (HW bei GH)", bis: 13 },
	{ label: "LieferantenNr (GH bei HW" , bis: 23},
	{ label: "Auftragsart", bis: 25 },
	{ label: "KundenAuftragsnr des HW", bis: 40 },
	{ label: "KundenauftragsText des HW", bis: 90 },
	{ label: "Vorgangsnummer des GH", bis: 105 },
	{ label: "Wunschlieferdatum des HW", bis: 113 },
	{ label: "Währungskennzeichen", bis: 116 },
	{ label: "Versionskennzeichen", bis: 121 },
	{ label: "Name Sachbearbeiter", bis: 161 },
	{ label: "Vorgangsdokumentendatum", bis: 169 },
	{ label: "Besteller/Abholer des HW", bis: 209 },
	{ label: "Lieferung KZ Komplett", bis: 210 },
	{ label: "Kundenstamm Kommission", bis: 220 },
]

const adressdatenfelder = [
	{label: "Satzart", bis: 3},
	{label: "Name 1", bis: 33},
	{label: "Name 2", bis: 63},
	{label: "Name 3", bis: 93},
	{label: "Straße", bis: 123},
	{label: "Land", bis: 126},
	{label: "PLZ", bis: 132},
	{label: "GPS Koordinaten", bis: 202},
	{label: "Format GPS", bis: 214},
	{label: "Lieferkontakt TelefonNr", bis: 244},
	{label: "Lieferkontakt Name", bis: 294},
	{label: "Lieferhinweis", bis: 344},
];

const positionsdatenfelder = [
	{label: "Satzart: Pos", bis: 3},
	{label: "PositionsNR des HW", bis: 13},
	{label: "PositionsNr des GH", bis: 23},
	{label: "Artikelnummer", bis: 38},
	{label: "Auftrag-/Nachfragemenge", bis: 49},
	{label: "Artikelbezeichnung 1", bis: 89},
	{label: "Artikelbezeichnung 2", bis: 129},
	{label: "Einzepreis Brutto je Preiseinheit", bis: 140},
	{label: "Preiseinheit gemäß Datanorm 4.0", bis: 141},
	{label: "Nettopositionswert", bis: 152},
	{label: "Rabatt 1", bis: 157},
	{label: "Rabatt 2", bis: 162},
	{label: "Leistungsverzeichnis-Nr", bis: 180},
	{label: "Kennz.-position", bis: 181},
	{label: "Positionstyp", bis: 182},
	{label: "Kennz.-vorbehaltlich technische Klärung", bis: 183},
	{label: "Mengeneinheit", bis: 186},
	{label: "Preis Kennz.", bis: 187},
	{label: "Lager Kennz.", bis: 188},
	{label: "MwSt %", bis: 193},
	{label: "Abschlagskennz.", bis: 194},
];

const pozFelder = [
	{label: "Satzart: Poz", bis: 3},
	{label: "PositionsNr des HW", bis: 13},
	{label: "PositionsNr des GH", bis: 23},
	{label: "Zuschlagstyp", bis: 25},
	{label: "Zuschlagsbezeichnung", bis: 105},
	{label: "Tagespreis (DEL-Notierung)", bis: 116},
	{label: "Nettopositionswert (Zuschlagsgesamtwert)", bis: 127},
];

const potFelder = [
	{label: "Satzart: Pot", bis: 3},
	{label: "Positionsnummer des HW", bis: 13},
	{label: "Positionsnummer des GH", bis: 23},
	{label: "Infotext 1", bis: 36},
	{label: "Infotext 2", bis: 103},
	{label: "Infotext 3", bis: 143},
	{label: "leistungsverzeichnisNr", bis: 161},
	{label: "Kennz.-Textanfang", bis: 126},
];

const endFelder = [
	{label: "Satzart", bis: 3},
	{label: "Zusatztext 1", bis: 43},
	{label: "Zusatztext 2", bis: 83},
	{label: "Zusatztext 3", bis: 123},
	{label: "Zusatztext 4", bis: 163},
]

const anfrageArten = {
	TB: "Abrufauftrag des HW beim GH",
	AN: "Anfrage des HW beim GH",
	PA: "Preisangebot des GH zum HW",
	BE: "Lieferauftrag des HW beim GH",
	A0: "Abruf des HW beim GH zur Lieferung aus einem Abrufauftrag",
	A1: "Abruf des HW beim GH zur Lieferung aus einem Angebot",
	A2: "Erstellen eines Abrufauftrags aus einem Angebot (HW->GH)",
	AA: "Abrufauftrag (GH->HW)",
	OR: "Eingangsbestätigung (GH->HW)",
	AB: "Bestellbest. des (GH zum HW)",
	LS: "Lieferavis (GH zum HW)",
	LF: "Lieferschein Final (GH zum HW) (nach Auslieferung)",
}

````

