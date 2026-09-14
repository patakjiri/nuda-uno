# nuda uno

Samostatný export interaktivního návrhu.

Zdrojový návrh SHA-256: 30d13dca21b2c64645feab3634a3ff7ea3fbe409cf50c1e13331c303dc306a3b

Provozní příklady používají prezentační data; změny se ukládají pouze v relaci prohlížeče.

Aktuální zdroj webu je `dist/index.html`, sdílený vzhled Studio je v `dist/studio.css`. Tón a terminologie jsou popsané v `COPYWRITING.md`.

Výchozí obrazovka Dnes používá rozložení s denními prioritami vlevo a schůzkami, provizním výpisem a vzděláváním vpravo. Týmový přehled staví vedle týmových případů výsledky jednotlivých poradců. Přepínání poradce i celé větve mění všechny odpovídající souhrny a seznamy; odkazy na vlastní výsledky poradce otevírají jeho vlastní agendu.

První otevření verze Studio přepne postranní menu do světlého vzhledu. Jednorázová migrace zachovává klienty, případy, podklady i další uložené údaje; následné změny vzhledu v nastavení se respektují.

Přílohy smluv zobrazují pouze prezentační metadata. Jejich odkazy záměrně nic neotevírají ani nestahují; skutečný soubor zatím není přiřazen.

Centrum oznámení rozlišuje pracovní upozornění, příležitosti z evidovaného kmene a zprávy od brokera či vedení organizace. Doporučení se počítají ze skutečných záznamů tohoto prezentačního prostředí a respektují vybraného poradce i celou větev. U chybějícího produktu výslovně rozlišují absenci v evidenci od skutečného stavu klientova krytí. Servisní případ má vazbu na smlouvu a opakované založení z obou vstupů otevře již existující případ. Odložení doporučení na sedm dní funguje i přes konec měsíce.

Přijaté organizační zprávy jsou prezentační obsah. Nové zprávy a odpovědi se ukládají pouze jako místní koncepty v relaci prohlížeče; aplikace nemá připojený příjem ani odesílání brokerovi. Přečtení oznámení, odložení a koncepty mají zachovaný stav po obnovení stejné relace. Vzhled centra je v `dist/notifications.css`.

Nastavení obsahuje profil, AI konektory, mobilní aplikaci a dokumentaci. Konfigurace konektorů lze vytvořit, upravovat, exportovat do JSON a odstranit. Vlastník je vždy Jan; členové týmu se vybírají výslovně a podřízení se nepřidávají automaticky. Provize mají samostatný scope. Rozepsané změny i konfigurace se ukládají v relaci prohlížeče, export obsahuje pouze specifikaci přístupu. Stav `configuration_only` a `endpoint: null` označují čekání na aktivaci skutečného serveru. V projektu není vzdálený MCP endpoint, OAuth server ani přístupové tokeny. Existující `document.modelContext` nástroje slouží pouze k navigaci a čtení aktuálního pohledu v podporovaném prohlížeči; nejde o vzdálený MCP server.

Sekce Mobilní aplikace představuje připravovanou aplikaci nuda uno pro iOS a Android. Karty App Store a Google Play mají stav Připravujeme a deaktivované stažení, protože skutečné odkazy a instalační balíčky zatím nejsou k dispozici. Návody k instalaci webu, manifest PWA, instalační eventy a kopírování adresy webu byly odstraněny. Produktová ikona zůstává v `dist/icons/app-192.png`. Vzhled je v `dist/settings.css`; mobil má vlastní viditelný vstup do Nastavení.

Zdrojové provize vycházejí z uživatelem zadaných modelových sazeb v `productCommissionRules`: majetkové pojištění 30 % ročního pojistného, ostatní neživotní pojištění (auto, cestovní, podnikatelé a flotily) 15 % ročního pojistného a hypotéky 1,5 % jistiny. Pojistná částka, hodnota nemovitosti, auta či firemní obrat se jako základ nepoužívají. Existující životní provize zůstávají samostatnými částkami poskytovatele, protože pro životní pojištění nebyla nová sazba zadána. V datech jsou hypotéky dosud rozpracované případy; jejich předpokládaná zdrojová provize se zobrazuje jako odhad a není účtována do výpisů.

Sazebník `SZ-2026.1` určuje provizi před kariérním rozdělením; pravidlo `RP-2026.1` následně dělí tuto částku rozdílově. Výpisy, podíly týmu, odvozené prezentační platby, storna i CSV používají opravené částky a uvádějí základ a produktovou sazbu. Zářijové nároky používají jiné smlouvy, aby jedna plná roční provize nebyla započtená dvakrát. Kontroly ověřují sazbu a základ smlouvy, shodu s neměnným zdrojovým snímkem, roční duplicity, haléřové rozdělení i platební saldo. Migrace `premium-rates-1` zachovává původní kontext reklamací, uživatelský text a přílohy. Pokud se změnilo přiřazení smlouvy, vyžaduje před dokončením rozepsané reklamace potvrzení nových podkladů.

## Mobilní pracovní prostředí

Do šířky 760 px se hlavní navigace otevírá hamburgerem v postranním panelu. Obsahuje všechny agendy, nastavení, podporu i profil. Panel blokuje pozadí, drží fokus uvnitř a obnovuje posun stránky po zavření; změna šířky odstraní mobilní zámek. Hledání se otevírá samostatnou ikonou, pracovní pohled se rozbaluje z viditelného souhrnu poradce a větve. Tyto ovladače nemění rozepsané formuláře. Tabulky se skládají do popsaných karet bez skrytí posledního sloupce, formuláře do jednoho sloupce. Mobilní vzhled doplňuje `dist/mobile.css`.

## Finanční profil a Open Banking

Klientská záložka Finanční profil je napojená na syntetická bankovní data Kláry Novotné (CL-01024). Rozlišuje odhad z transakcí, potvrzení klientem a platbu spárovanou s existující smlouvou. Průměry vycházejí z června–srpna 2026, vlastní převody jsou vyloučené. Ověření, rozepsané formuláře a koncept žádosti jsou místní stav relace v `state.banking`; žádné bankovní připojení ani odeslání žádosti neprobíhá. Interakce a styly jsou v `dist/index.html` a `dist/banking.css`. Přímý odkaz na ukázku používá `#client/CL-01024/banking`.

## GitHub Pages

Repository: `patakjiri/nuda-uno`. In Settings → Pages select GitHub Actions. Pushes to main publish dist automatically. Expected URL after successful deployment: https://patakjiri.github.io/nuda-uno/

Local preview: `python3 -m http.server 8080 --directory dist`.
