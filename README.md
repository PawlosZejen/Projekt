Jan Kozłowski 117364
Adrian Lachowicz 117262
Paweł Gronostajski 117263

1. Cel projektu
Celem projektu jest zaprojektowanie i zamodelowanie systemu informatycznego, który zarządza funkcjonowaniem nekromantycznej biblioteki żywych ksiąg. System ma umożliwiać kontrolę zachowania ksiąg, ich wypożyczania, karmienia, monitorowania nastroju, reagowania na incydenty, obsługi klątw oraz zarządzania relacjami między księgami.
Projekt ma zostać wykonany w formie kompletnej dokumentacji UML oraz opisu funkcjonalnego systemu.

2. Zakres funkcjonalny systemu
System musi obsługiwać następujące obszary:
2.1. Zarządzanie żywymi księgami
System powinien umożliwiać:
rejestrowanie nowych ksiąg,
monitorowanie ich parametrów (moc magiczna, głód, korupcja, temperament, lojalność),
śledzenie ich aktualnego stanu (Calm, Curious, Mischievous, Hungry, Irritated, Feral, Corrupted, Dormant, Sealed, Evolving, Merged),
obsługę karmienia ksiąg różnymi typami „pokarmu” (światło, kurz, wspomnienia, emocje),
wykrywanie prób ucieczki,
izolowanie ksiąg niebezpiecznych,
oczyszczanie ksiąg skażonych.
2.2. Wypożyczanie ksiąg
System musi umożliwiać:
wypożyczanie ksiąg przez użytkowników o odpowiednim poziomie rangi,
ocenę ryzyka wypożyczenia (na podstawie temperamentu i mocy księgi),
przedłużanie wypożyczeń,
naliczanie kar za spóźnienia,
blokowanie wypożyczeń ksiąg niebezpiecznych.
2.3. Zarządzanie użytkownikami
System powinien obsługiwać:
Adeptów Biblioteki,
Mistrzów Bibliotekarzy,
Strażników Zaklęć.
Każdy użytkownik ma parametry takie jak: ranga, odporność na klątwy, reputacja, maksymalny poziom niebezpieczeństwa ksiąg, które może wypożyczać.
2.4. System incydentów
System musi rejestrować i obsługiwać:
ucieczki ksiąg,
ataki ksiąg na użytkowników,
rzucanie klątw,
konflikty między księgami,
przypadki korupcji magicznej
Każdy incydent ma typ, poziom zagrożenia, księgę źródłową i osobę zgłaszającą.
2.5. System relacji między księgami
System musi śledzić:
poziom wrogości między księgami,
poziom synergii,
przewidywanie konfliktów,
przewidywanie współpracy,
możliwość połączenia dwóch ksiąg w jeden tom.
2.6. System klątw i błogoławieństw
System powinien:
monitorować aktywne klątwy rzucone przez księgi,
umożliwiać zdejmowanie klątw przez Strażników Zaklęć,
oceniać ryzyko rzucenia klątwy przez księgę.
2.7. System ewolucji ksiąg
Księgi mogą:
zmieniać temperament,
zdobywać nowe zaklęcia,
mutować,
zwiększać moc magiczną,
łączyć się z innymi księgami.
2.8. System karmienia
System musi:
przechowywać harmonogram karmienia,
określać, kiedy księga wymaga pokarmu,
reagować na przekarmienie lub niedożywienie.
3. Wymagane moduły systemu
Projekt musi zawierać co najmniej następujące moduły:
Book Management Module – zarządzanie księgam
User Management Module – zarządzanie użytkownikami
Borrowing Module – wypożyczenia
Incident Handling Module – obsługa incydentów
Curse & Blessing Module – klątwy i błogosławieństwa
Feeding Module – karmienie ksiąg
Evolution Module – ewolucja i mutacje ksiąg
Interaction Matrix Module – relacje między księgami
Escape Monitoring Module – wykrywanie ucieczek
Corruption Engine – analiza skażenia magicznego

4. Wymagane klasy (minimalny zestaw)
LivingBook
title, temperament, magicPower, hungerLevel, corruptionLevel, loyaltyLevel, escapeProbability, preferredFoodType, state

feed(), attemptEscape(), castMinorCurse(), purify(), seal(), interactWith()

Spell
type, dangerLevel, manaCost, forbidden

invoke(), evaluateRisk()

User
rank, curseResistance, reputation, allowedDangerLevel

borrowBook(), reportIncident(), attemptCalmBook()

Borrowing
dueDate, riskLevel

extend(), calculatePenalty()

IncidentReport
type, severity

escalate(), assignToKeeper()

FeedingSchedule
foodType, interval, lastFed

shouldFeed(), updateLastFed()

BookKeeper
specialization, responseTime

isolateBook(), neutralizeCurse(), handleEscapeAttempt()

BookInteractionMatrix
hostilityLevel, synergyLevel

updateInteraction(), predictConflict(), predictCooperation()

CorruptionEngine
corruptionThreshold

evaluate(), triggerContainment(), spreadRisk()

EscapeMonitoringSystem
detectEscape(), lockSection(), summonKeeper()
