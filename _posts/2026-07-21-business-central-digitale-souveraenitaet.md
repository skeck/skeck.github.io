---
title: "Business Central und digitale Souveränität: Welchen Spielraum gibt es (noch)?"
date: 2026-07-21 00:00:00 +0200
lang: de-DE
permalink: /posts/business-central-digitale-souveraenitaet/
categories: [Business Central, Digital Sovereignty]
tags: [business-central, digital-sovereignty, cloud, ai-agents, mcp, on-premises]
description: "Wie souverän bleibt Business Central zwischen On-Premises, Cloud, AI-Agents, MCP, GitHub und Azure-Telemetrie?"
---

> English version: [Business Central and Digital Sovereignty: How Much Room to Maneuver Is Left?](/posts/business-central-digital-sovereignty/)

Selbstbestimmung und eine geringere Abhängigkeit von Big Tech gehören sicherlich zu den wichtigsten Herausforderungen unserer Zeit. Auch im Business-Central-Umfeld halte ich diese Frage nach wie vor für fundamental. Gleichzeitig überschlagen sich die Rahmenbedingungen, und es wird zunehmend schwierig, den Überblick zu behalten.

Business Central On-Premises ist weiterhin verfügbar. Microsofts strategische Richtung ist dennoch eindeutig: Die Cloud-Transformation gilt als abgeschlossen, die sichtbare Produktinnovation konzentriert sich inzwischen stark auf AI-Funktionen und AI-Agents. Bereits mit der 2021 angekündigten und 2022 aktivierten [Universal-Code-Initiative](https://www.microsoft.com/en-us/dynamics-365/blog/it-professional/2022/10/28/the-dynamics-365-business-central-universal-code-initiative-is-live/) machte Microsoft die cloudoptimierte Extension-Architektur auch für neue On-Premises-Installationen zum Normalfall. Mehrere Bridge-to-the-Cloud-Promotions flankieren seit Jahren den Wechsel zu Business Central Online. Seit April 2025 erhalten Neukunden Business Central On-Premises zudem nicht mehr als unbefristete Lizenz, sondern nur noch im [Subscription-Modell](https://techcommunity.microsoft.com/t5/business-applications-for/simplifying-licensing-across-our-smb-erp-solutions-don-t-miss/m-p/3808035). Microsoft hält On-Premises damit formal offen, lenkt das kommerzielle und technologische Modell aber klar in Richtung Cloud und Subscription.

Wer Business Central On-Premises betreibt, kontrolliert Service Tier, SQL-Datenbank, Netzwerk und Backups. Doch sobald AI-Funktionen, AI-Agents, Telemetrie oder moderne DevOps-Prozesse ins Spiel kommen, verlässt ein wachsender Teil der Architektur das eigene Spielfeld. Die übliche Frage „SaaS oder On-Premises?“ greift deshalb oft zu kurz. Strategisch entscheidend ist keine Schwarz-Weiß-Betrachtung, sondern ein genauer Blick auf die einzelnen Schichten: Welche Teile können Unternehmen weiterhin selbst betreiben, ersetzen oder in eine europäische Betriebsumgebung verschieben, ohne Business Central als ERP-Plattform aufzugeben?

Wo Microsoft auf offene Schnittstellen, Standards oder Open Source setzt, bleiben Alternativen grundsätzlich möglich. Entscheidend ist jedoch nicht nur, ob sich ein Dienst ansprechen lässt, sondern ob sich der dahinterliegende Dienst auch ersetzen oder in einer anderen Betriebsumgebung ausführen lässt. Solange zentrale Plattformdienste – etwa die Ausführung von AI-Agents, die Telemetrieauswertung oder Teile der Entwicklungsplattform – ausschließlich vom Anbieter bereitgestellt werden, entsteht eine strukturelle Abhängigkeit. Die entscheidende Souveränitätsgrenze verläuft deshalb nicht einfach zwischen Cloud und On-Premises, sondern zwischen Diensten, die austauschbar bleiben, und Diensten, deren Betrieb ausschließlich beim Plattformanbieter liegt.

Für kontrollorientierte oder regulierte Organisationen ist das relevant: Der ERP-Kern kann weiterhin lokal oder regional betrieben werden. Die Einschränkung liegt außerhalb dieses Kerns und betrifft die Innovationsschicht. Copilot-Funktionen, native AI-Agents, der offizielle Business-Central-MCP-Server, Teile der Power-Platform-Integration, die produktisierte Telemetrieauswertung und GitHub-zentrierte Entwicklungsprozesse entstehen primär in Microsofts Cloud-Ökosystem und stehen On-Premises teilweise nicht oder nur über eigene Integrationen zur Verfügung.

> **Der ERP-Kern ist hostbar. Die Innovationsschicht ist Cloud-first.**

On-Premises löst die Souveränitätsfrage damit nicht. Es bewahrt aber einen wichtigen Ausgangspunkt: Daten, Geschäftslogik und zentrale Betriebsprozesse müssen nicht vollständig in der Microsoft Cloud aufgehen.

## Welche Souveränität ist eigentlich gemeint?

In Diskussionen über digitale Souveränität vermischen sich aus meiner Sicht häufig drei unterschiedliche Fragen.

Die erste betrifft Datenschutz und Compliance: Wo werden Daten gespeichert, wer darf darauf zugreifen, wie werden Zugriffe protokolliert und welche regulatorischen Anforderungen lassen sich nachweisen?

Die zweite betrifft die Betriebs- und Plattformhoheit: Kann ein Dienst in einer anderen Betriebsumgebung ausgeführt werden? Lässt sich der zugrunde liegende Plattformdienst selbst betreiben oder ersetzen? Kann ein Unternehmen den Modellanbieter wechseln oder eine eigene Implementierung betreiben?

Die dritte ist strategischer Natur: Wer bestimmt die Produktroadmap, die Schnittstellen und die Bedingungen, unter denen eine zentrale Komponente künftig genutzt werden kann?

Diese Ebenen hängen zusammen, sind aber nicht dasselbe. Ein Dienst kann sehr gut abgesichert und regulatorisch sauber betrieben sein, ohne deshalb architektonisch austauschbar zu werden. Umgekehrt macht eine offene Schnittstelle noch keine produktionsreife Alternative.

Digitale Souveränität kann meiner Meinung nach nicht nur über Hosting und Datenschutz diskutiert werden. Je stärker sich Business Central mit GitHub, AI, MCP und AI-Agent-Systemen integriert, desto deutlicher wird für mich, dass die langfristigen Abhängigkeiten zunehmend außerhalb der klassischen ERP-Datenbank entstehen.

## Was Microsoft in Business Central Online bereits adressiert

Wer heute über Microsoft Cloud und europäische Anforderungen spricht, sollte fairerweise anerkennen, wie viel sich in den vergangenen Jahren verändert hat. Einige Diskussionen wirken noch so, als befänden wir uns auf dem Stand von 2019. Tatsächlich hat Microsoft erheblich in Datenresidenz, Verschlüsselung, Governance und kontrollierte Administrationszugriffe investiert.

Business Central Online wird in einer ausgewählten Azure-Region bereitgestellt. Für europäische Kunden ist zusätzlich die [EU Data Boundary](https://learn.microsoft.com/en-us/privacy/eudb/eu-data-boundary-learn) relevant, mit der Microsoft die Speicherung und Verarbeitung von Kundendaten für einen großen Teil seiner kommerziellen Cloud-Dienste innerhalb der EU und der EFTA zusagt. Solche Zusagen lösen nicht jede Rechtsfrage. Sie sind aber auch nicht bedeutungslos. Datenresidenz reduziert Übertragungen, vereinfacht Governance und schafft eine klarere technische und organisatorische Grenze.

Für Business Central kommen konkrete Schutzmechanismen hinzu. Über die Verknüpfung einer Business-Central-Umgebung mit einer Power-Platform-Umgebung können Kunden [kundenseitig verwaltete Schlüssel](https://learn.microsoft.com/en-us/dynamics365/business-central/admin-customer-managed-encryption-key) einsetzen. Damit wird die Verschlüsselung nicht vollständig aus Microsofts Plattform herausgelöst, aber die Kontrolle über den Lebenszyklus des Schlüssels steigt. Microsoft dokumentiert außerdem [Customer Lockbox](https://learn.microsoft.com/en-us/dynamics365/business-central/admin-customer-lockbox) für Business Central. Damit können Organisationen Zugriffe von Microsoft-Supportmitarbeitern auf Kundendaten in bestimmten Supportfällen explizit genehmigen oder ablehnen und nachvollziehen.

Bei Identitäten und Governance liegt eine weitere Stärke des Microsoft-Ökosystems. Entra ID, Conditional Access, Privileged Identity Management, Audit- und Compliance-Funktionen sowie die Werkzeuge aus Microsoft Purview erlauben ein Kontrollniveau, das viele Unternehmen zumindest im Eigenbetrieb nur mit erheblichem Aufwand erreichen würden. Gerade das gehört aus meiner Sicht zu einer fairen Souveränitätsbewertung: Eigenbetrieb bedeutet nicht automatisch bessere Governance.

### Der CLOUD Act macht nicht alle Maßnahmen wertlos

Rund um den [CLOUD Act](https://www.congress.gov/bill/115th-congress/house-bill/4943) begegnet mir häufig die Aussage, sämtliche technischen und organisatorischen Schutzmaßnahmen seien letztlich nutzlos, weil amerikanische Behörden im Zweifel ohnehin auf alle Daten zugreifen könnten. Diese Schlussfolgerung halte ich für zu einfach.

Der CLOUD Act schafft keinen allgemeinen Echtzeit- oder Direktzugriff amerikanischer Behörden auf Cloudsysteme. Er regelt unter anderem, unter welchen Voraussetzungen US-Anbieter auf Grundlage rechtlich wirksamer Anordnungen Daten herausgeben müssen, die sich in ihrem Besitz, ihrer Verwahrung oder unter ihrer Kontrolle befinden. Der physische Speicherort allein beseitigt diese Möglichkeit daher nicht.

Daraus folgt aber nicht, dass Dinge wie Datenresidenz, Verschlüsselung, Zugriffskontrollen, Schlüsselverwaltung oder Lockbox wertlos wären. Sie reduzieren die Zahl möglicher Zugriffspfade, begrenzen interne Berechtigungen, verbessern Nachvollziehbarkeit und können beeinflussen, welche Daten ein Anbieter technisch überhaupt im Klartext bereitstellen kann. Hinzu kommen rechtliche Prüfungen, Anfechtungsmöglichkeiten und Benachrichtigungsregeln, soweit diese im konkreten Fall zulässig sind. Der CLOUD Act ist ein relevantes Rechtsraumrisiko. Er ist aber kein Generalschlüssel für sämtliche Daten europäischer Cloudkunden.

Ebenso wenig ist ein europäischer Speicherort ein vollständiger Schutz vor staatlichen Zugriffen. Auch europäische Staaten kennen Herausgabe- und Überwachungsbefugnisse. Die sinnvolle Frage lautet daher nicht, ob irgendein Zugriff theoretisch ausgeschlossen werden kann. Entscheidend ist, welche Rechtsgrundlagen gelten, welche technischen Zugriffsmöglichkeiten bestehen, wie transparent Verfahren sind und welche Schutzschichten ein Unternehmen selbst kontrolliert. Die konkrete datenschutzrechtliche Bewertung hängt deshalb vom Einsatzfall, den verarbeiteten Daten und den vereinbarten technischen und organisatorischen Schutzmaßnahmen ab.

Microsoft versucht die verbleibende Unsicherheit zusätzlich durch seine [European Digital Commitments](https://blogs.microsoft.com/on-the-issues/2025/04/30/european-digital-commitments/) und die Angebote der [Microsoft Sovereign Cloud](https://blogs.microsoft.com/on-the-issues/2025/06/16/microsoft-sovereign-cloud/) zu adressieren. Dazu gehören europäische Betriebs- und Governance-Optionen sowie Zusagen zur betrieblichen Kontinuität. Auch diese Maßnahmen ändern nicht die Eigentümerstruktur und ersetzen keine eigene Risikoabwägung. Sie zeigen aber, dass die Diskussion nicht bei „US-Anbieter gleich ungeschützt“ stehen bleiben sollte.

### AI-Funktionen und AI-Agents werden gesondert behandelt

Bei AI muss man genauer hinsehen, weil sich Datenflüsse und Produktzusagen je nach Dienst unterscheiden. Microsoft trennt Consumer-Angebote, Microsoft-365- und Dynamics-Copilots sowie Azure-AI-Dienste vertraglich und technisch voneinander. Für [Copilot-Funktionen in Dynamics 365 und Power Platform](https://learn.microsoft.com/en-us/dynamics365/faqs-copilot-data-security-privacy) sowie für [Azure-AI-Dienste](https://learn.microsoft.com/en-us/azure/foundry/responsible-ai/openai/data-privacy) dokumentiert Microsoft produktbezogene Zusagen: Prompts, Ausgaben und Kundendaten werden grundsätzlich nicht zum Training oder zur Verbesserung der zugrunde liegenden Modelle verwendet, sofern der Kunde beziehungsweise Mandantenadministrator einer entsprechenden Datennutzung nicht ausdrücklich zustimmt. Das ist ein wichtiger Unterschied zu öffentlichen Consumer-Diensten.

Für Business Central bedeutet das trotzdem nicht, dass jede AI-Funktion innerhalb derselben Daten- und Betriebsgrenzen wie die ERP-Datenbank ausgeführt wird. Native AI-Agents und Copilot-Funktionen nutzen von Microsoft bereitgestellte Cloud-Dienste für Modellzugriff und Orchestrierung. Welche Modelle und Regionen verfügbar sind, welche Diagnose- und Missbrauchsüberwachung greift und welche Daten für den Betrieb verarbeitet werden, hängt von der jeweils eingesetzten Business-Central-Funktion ab.

Die richtige Prüfung lautet deshalb nicht nur: „Wird mit meinen Daten trainiert?“ Ebenso wichtig sind Fragen nach Verarbeitungsregion, Aufbewahrung, Protokollierung, Modellprovider, Toolzugriffen und Freigaben.

Business Central ergänzt diese allgemeinen Zusagen um konkrete Steuerungsmöglichkeiten. Administratoren können einzelne Copilot- und Agentfunktionen aktivieren oder deaktivieren, Benutzerzugriffe über Berechtigungen steuern und – falls die Verarbeitung in einer anderen Geografie stattfindet – regionsübergreifende Datenbewegungen erlauben oder unterbinden. Microsoft beschreibt diese Kontrollen in der [Business-Central-Dokumentation zu Copilot- und Agentfunktionen](https://learn.microsoft.com/en-us/dynamics365/business-central/enable-ai). Bei den derzeit verfügbaren nativen AI-Agents kommen [eigene Benutzeridentitäten und zugewiesene Berechtigungssätze](https://learn.microsoft.com/en-us/dynamics365/business-central/payables-agent) sowie [nachvollziehbare Aufgabenverläufe mit menschlichen Prüfschritten](https://learn.microsoft.com/en-us/dynamics365/business-central/supervise-agent-tasks) hinzu.

Das sind reale Schutzmaßnahmen für Datenschutz, Governance und sicheren Betrieb. Sie ändern jedoch nichts daran, dass die Ausführung der AI-Funktionen und AI-Agents innerhalb der von Microsoft bereitgestellten Plattformdienste erfolgt.

## Modelle und Infrastruktur: Europäische Optionen im Microsoft-Stack

Auch bei Modellen und Rechenkapazität zeigt sich dieses gemischte Bild. Europa verfügt über eigene Anbieter und Open-Weight-Modelle. Open Weight bedeutet, dass die trainierten Modellgewichte, vereinfacht gesagt die im Training erlernten Parameter, verfügbar sind. Trainingsdaten, Trainingscode und Nutzungsrechte sind damit nicht automatisch offen. Europa verfügt aber noch nicht über einen vergleichbaren integrierten Stack aus Frontier-Modell, Hyperscale-Compute, globaler Cloud, Entwicklerökosystem und Enterprise-Vertrieb. Die EU investiert mit [AI Factories und geplanten Gigafactories](https://commission.europa.eu/topics/competitiveness/ai-continent_en) in eigene Kapazitäten. Microsoft baut zugleich [seine deutschen Rechenzentren aus](https://news.microsoft.com/source/emea/2026/03/spatenstich-fuer-rechenzentrums-cluster-in-nordrhein-westfalen-microsoft-staerkt-die-digitale-infrastruktur-fuer-deutschlands-ki-zukunft/?lang=de). Beides verbessert die europäische Infrastruktur, ändert aber nicht automatisch, wer die Plattform, ihre zentralen Verwaltungsdienste und die Produktstrategie kontrolliert.

### Microsoft und Mistral: Mehr Wahlfreiheit, aber kein europäischer Komplett-Stack

Die im Juli 2026 deutlich erweiterte [Partnerschaft zwischen Microsoft und dem französischen AI-Anbieter Mistral](https://www.prnewswire.com/in/news-releases/microsoft-and-mistral-expand-strategic-partnership-to-give-enterprises-and-regulated-industries-frontier-ai-they-can-control-302830228.html) finde ich ziemlich interessant. Microsoft will im Milliardenumfang Teile der von Mistral in Europa aufgebauten GPU-Infrastruktur nutzen. Gleichzeitig werden Mistral Medium 3.5 und OCR 4 über Microsoft Foundry angeboten; [Medium 3.5 steht außerdem in Copilot Studio zur Modellauswahl](https://www.microsoft.com/en-us/microsoft-copilot/blog/copilot-studio/mistral-joins-copilot-studios-growing-lineup-of-model-providers/). Über Azure Local sollen sich bestimmte Open-Weight-Modelle von Mistral zudem in kundeneigenen und bis hin zu vollständig getrennten Umgebungen betreiben lassen.

Das ist mehr als nur ein weiteres Modell im Azure-Katalog. Auf Modellebene entsteht eine europäische Alternative, auf Infrastrukturebene zusätzliche europäische Rechenkapazität und auf Betriebsebene zumindest für bestimmte Modelle eine echte lokale oder isolierte Option. Gerade für regulierte Organisationen ist das aus meiner Sicht relevant.

Für Business Central liegt der unmittelbarste Nutzen zunächst außerhalb der nativen AI-Agents. Ein Copilot-Studio-Agent kann Business Central Online über den Connector oder den Business Central MCP Server anbinden und dabei (derzeit noch als experimentelle Option) Mistral Medium 3.5 als Modell verwenden. Für eigene Integrationen, auch in On-Premises-Szenarien, finde ich [OCR 4](https://techcommunity.microsoft.com/blog/azure-ai-foundry-blog/mistral-document-ai-with-ocr-4-and-mistral-medium-3-5-arrive-in-microsoft-foundr/4529863) fast noch interessanter: Ein kontrolliert betriebener Dienst könnte Rechnungen oder andere Geschäftsdokumente analysieren und die strukturierten Ergebnisse an Business Central zurückgeben.

Vollständige europäische Unabhängigkeit entsteht dadurch trotzdem nicht. Microsoft Foundry, Copilot Studio und Azure Local bleiben Microsoft-Plattformen, und die europäische Recheninfrastruktur basiert unter anderem auf Nvidia-Hardware. Gleichzeitig wird Microsoft zu einem wichtigen Vertriebspartner und Großabnehmer eines europäischen Modellanbieters.

Ich würde die Partnerschaft deshalb weder als vollständigen europäischen AI-Stack feiern noch als bloßes Souveränitätsmarketing abtun. Sie schafft reale zusätzliche Wahlmöglichkeiten innerhalb eines weiterhin eng verflochtenen europäischen und amerikanischen Ökosystems. Für mich bestätigt das eher die Kernthese dieses Artikels: Entscheidend ist nicht nur, aus welchem Land ein Anbieter kommt, sondern welche Teile eines Dienstes austauschbar, selbst betreibbar und langfristig kontrollierbar bleiben.

## Entwicklung und DevOps: Offenheit unter Konsolidierungsdruck

Große Teile der Entwicklungsschicht sind, insbesondere im Vergleich zur C/AL- und C/SIDE-Vergangenheit, offen angelegt: Visual Studio Code basiert auf dem quelloffenen Code-OSS-Projekt, [AL-Go for GitHub](https://github.com/microsoft/AL-Go) ist Open Source, und auch große Teile der in AL entwickelten Basis- und Systemanwendungen sind im [BCApps-Repository](https://github.com/microsoft/BCApps) öffentlich einsehbar. Die eigentliche Business-Central-Plattform bleibt dagegen proprietär.

Auch bei Coding-Agents setzt sich dieses gemischte Bild fort. Seit Frühjahr 2026 dokumentiert Microsoft einen eigenständigen [AL MCP Server](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/al-agent-tools/al-mcp-server). Er läuft als separater Prozess und stellt AL-Werkzeuge wie Build, Compile, Publish, Symbolsuche und Diagnostik jedem MCP-kompatiblen Coding-Agenten zur Verfügung. Das ist ausdrücklich nicht auf einen Microsoft-Coding-Agenten beschränkt und kann lokal oder in einer eigenen Automatisierungsumgebung betrieben werden.

Gleichzeitig konsolidiert sich der Markt schnell. Continue.dev war ein modellflexibler Coding-Assistent, den ich selbst gerne genutzt habe. Inzwischen wurde das Projekt [von Cursor übernommen](https://www.continue.dev/). Kurz darauf wurde die [vereinbarte, aber noch nicht vollzogene Übernahme von Anysphere, dem Unternehmen hinter Cursor, durch SpaceX](https://www.sec.gov/Archives/edgar/data/1181412/000162828026043411/spaceexplorationtechnologi.htm) bekannt. Die zeitliche Nähe beweist keinen kausalen Zusammenhang. Sie zeigt aber, wie schnell sich Eigentümer- und Betreiberstrukturen auch bei Werkzeugen verändern, die zunächst als offene Alternative wahrgenommen werden.

Umso bemerkenswerter ist, dass ausgerechnet GitHub in einzelnen Bereichen wieder mehr Wahlfreiheit eröffnet. [Copilot CLI unterstützt eigene Modellprovider und einen Offline-Modus](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/use-byok-models), darunter OpenAI-kompatible Endpunkte und lokal betriebene Modelle über Ollama, vLLM oder Foundry Local. Der Kontakt zu GitHub-Servern kann dabei unterbunden werden, sofern auch der Modellprovider innerhalb der isolierten Umgebung läuft.

Das macht GitHub Copilot insgesamt nicht souverän. Die Funktion gilt für die CLI und nicht automatisch für alle IDE- und Cloudfunktionen. Sie zeigt aber, dass der Modellanbieter in einem konkreten Entwicklungsablauf austauschbar sein kann.

Der Wechsel von Azure DevOps zu GitHub und der darauf basierenden Microsoft-Lösung AL-Go gehört für viele BC-Partner und Kunden zu den wichtigsten Plattformentscheidungen der vergangenen Jahre. Microsoft liefert damit einen einheitlichen, gepflegten DevOps-Pfad. Gleichzeitig entsteht eine Bindung an GitHub als US-Cloud-Plattform.

GitHub Enterprise Cloud mit [Data Residency](https://docs.github.com/en/enterprise-cloud@latest/admin/data-residency/about-github-enterprise-cloud-with-data-residency), kurz GHE.com, erweitert den Spielraum. Repositories und Actions-Daten können in einer gewählten Region, darunter der EU, gespeichert werden. Das ist eine relevante Datenresidenzoption, aber keine europäische Developer-Plattform. Anbieter sowie zentrale Steuerungs- und Verwaltungsdienste bleiben bei GitHub beziehungsweise Microsoft.

Die offiziellen AL-Go-Repositories und Templates sind auf GitHub.com ausgerichtet; GHE.com ist damit bislang kein regulärer Microsoft-Supportpfad. [Freddy](https://github.com/freddydk), ursprünglicher Autor von AL-Go und BcContainerHelper, pflegt jedoch einen [Downstream-Fork mit einem eigenen GHE.com-Szenario](https://github.com/Freddy-DK/AL-Go/blob/main/Scenarios/UsingGitHubEnterprise.md), der die Toolchain gezielt an GHE.com anpasst. Hoffentlich kommt das zurück in den Standard :)

## MCP und AI-Agents: Technisch offen, operativ anspruchsvoll

Am deutlichsten zeigt sich das Spannungsfeld bei AI-Agents.

Microsoft integriert native AI-Agents tief in Business Central Online. Diese AI-Agents bearbeiten mehrstufige Geschäftsprozesse und werden über Berechtigungen, Aufgaben, Profile, sichtbare Seiten und Benutzerinteraktionen gesteuert. Mit dem [Agent SDK for AL](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/ai/ai-agent-sdk-overview) können Partner eigene AI-Agents programmatisch definieren.

Nicht frei austauschbar sind jedoch die darunterliegende Modellanbindung und die Orchestrierung. Business Central kann zwischen den in der Microsoft-Umgebung verfügbaren Modellen wählen. Microsoft dokumentiert derzeit keine Möglichkeit, einen beliebigen lokalen oder europäischen Modellendpunkt als Modellanbieter für die nativen AI-Agents zu konfigurieren. Daran ändert auch die erweiterte Microsoft-Mistral-Partnerschaft zunächst nichts: Medium 3.5 ist für Microsoft Foundry und Copilot Studio verfügbar, aber bislang nicht als frei konfigurierbarer Modellanbieter für native Business-Central-AI-Agents. Ein wesentlicher Teil des Agent-Moduls ist zwar in AL einsehbar, die Ausführung zentraler Funktionen erfolgt jedoch (vermutlich) in proprietären Plattformdiensten.

Wer also die native, tief integrierte AI-Agent-Funktionalität nutzen möchte, ist damit an Business Central Online gebunden. Eigene AI-Integrationen in On-Premises bleiben möglich. Sie sind dann jedoch eigene investitionsintensive Softwarelösungen und nicht dieselbe Produktfunktion.

Auch sollte zuerst zwischen mehreren Angeboten unterschieden werden:

- Der **AL MCP Server** ist ein lokal ausführbares Entwicklungswerkzeug für Coding-Agents.
- Der **Business Central MCP Server** stellt Geschäftsdaten und Business-Central-APIs als Tools bereit und ist offiziell nur für [Business Central Online](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/ai/configure-mcp-server) dokumentiert.
- Der **Admin Center MCP Server**, derzeit in [Public Preview](https://learn.microsoft.com/en-us/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/connect-ai-agents-admin-center-through-mcp-server), adressiert Verwaltungs- und Betriebsaufgaben im Business Central Admin Center.
- **Native AI-Agents in Business Central** werden durch Microsofts Plattformdienste innerhalb von Business Central Online ausgeführt.

Das Model Context Protocol (MCP) ist ein offener Standard. Es erlaubt AI-Anwendungen, Werkzeuge und Datenquellen auf einheitliche Weise zu entdecken und aufzurufen. Der offizielle Business Central MCP Server ist dennoch ein Microsoft-gehosteter Produktendpunkt. Ob dieser künftig auch für On-Premises bereitgestellt wird, ist meiner Meinung nach eine offene Frage. Es gibt Hinweise in beide Richtungen.

Eine Alternative wären daher eigene MCP-Server. Community-Projekte wie [SShadowS/business-central-mcp](https://github.com/SShadowS/business-central-mcp) zeigen, dass das technisch realisierbar ist.

Damit sind auch AI-Agents für Business Central On-Premises grundlegend eine reale Option: Ein eigener MCP-Server übersetzt Business-Central-APIs in fachlich begrenzte Tools. Eine externe AI-Agent-Plattform verwendet ein lokales, europäisches oder anderweitig kontrolliertes Modell. Eine eigene AL-Extension in Business Central könnte Aufgaben, Berechtigungen, Freigaben und Audit-Informationen verwalten. Ein externer Dienst, etwa auf Basis des [Microsoft Agent Framework](https://github.com/microsoft/agent-framework) oder eines Open-Source-Orchestrators wie LangGraph, führt die AI-Agent-Läufe aus und schreibt Ergebnisse zurück.

Eine wirklich produktive AI-Agent-Plattform als On-Premises-Lösung dürfte jedoch einiges an Investitionen erfordern. Sie benötigt eine AL-Extension für Konfiguration und Benutzeroberfläche, einen dauerhaft betriebenen externen Dienst, persistente Aufgaben- und Ausführungszustände, eine kontrollierte Schnittstellen- und Tool-Schicht, Freigaben, Protokollierung, Security, Idempotenz, Fehlerbehandlung, Monitoring und ein Updateverfahren. Diese Option ist deshalb vor allem dort sinnvoll, wo Modellort, Governance und langfristige Wahlfähigkeit den Aufbau einer eigenen oder gemeinschaftlich getragenen Plattform rechtfertigen.

## Telemetrie: Hier bleibt die Azure-Bindung

Bei der Telemetrie ist das Bild eindeutiger.

Business Central kann sowohl aus SaaS- als auch aus On-Premises-Umgebungen strukturierte Telemetrie an [Azure Application Insights](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-overview) senden. Microsoft stellt darauf aufbauend [Power-BI-Apps](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-power-bi-app) für Nutzung, Fehler, Performance und Administration bereit. Im Online-Betrieb umfasst der Telemetriekatalog zusätzlich Agent Lifecycle, AI Consumption sowie MCP-Konfigurationen und Toolaufrufe.

Damit wird Telemetrie zu einer wichtigen Kontroll- und Auswertungsschicht für AI-Agents und MCP. Sie zeigt, welche AI-Agents und Tools verwendet werden, wie lange Aufrufe dauern und wo Fehler oder unerwartetes Verhalten auftreten.

Ein eigener [`IngestionEndpoint`](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-control-cost#use-a-custom-endpoint) wirkt zunächst wie eine Ausweichmöglichkeit. Microsoft dokumentiert, dass ein eigener Endpoint vorgeschaltet werden kann, um Daten zu filtern, anzureichern oder in einen anderen Datenspeicher weiterzuleiten. Das ist technisch relevant, aber noch keine fertige alternative Telemetrieplattform.

Der dokumentierte und produktisierte Standardpfad bleibt Application Insights. Die offiziellen Power-BI-Apps verbinden sich direkt mit einer Application-Insights-Ressource. Wer die gesamte Telemetrielösung ersetzen will, muss nicht nur einen eigenen Ingestion Endpoint betreiben, sondern auch Speicherung, Abfragen, Alarmierung, Dashboards, Berechtigungen und laufende Kompatibilität selbst lösen.

Das ist möglich, aber keine realistische Standardoption für normale Business-Central-Projekte. Azure Application Insights bleibt bei der Business-Central-Telemetrie der de-facto-Standardpfad.

## Nicht jede Abhängigkeit muss ersetzt werden

Ich halte es für wichtig, Abhängigkeiten nüchtern zu betrachten. Wer ihre Grenzen kennt, kann sie bewusst akzeptieren. Wer sie ignoriert, gibt Wahlfreiheit oft unbemerkt auf. Digitale Souveränität bedeutet für mich nicht vollständige Autarkie. Unternehmen müssen nicht jede Cloudfunktion selbst entwickeln. Sie sollten aber wissen, wo eine zweite Betriebsoption existiert und wo nicht.

Für wichtige Prozesse ist eine Degradationsstrategie oft hilfreicher als ein pauschales Cloudverbot:

- Können kritische Hotfixes gebaut werden, wenn GitHub vorübergehend nicht erreichbar ist?
- Welche manuellen Abläufe bleiben, wenn AI-Funktionen deaktiviert werden?
- Welche Betriebsinformationen sind ohne Application Insights sichtbar?

Die Souveränitätsfrage verschiebt sich damit vom ERP-Kern auf die gesamte Prozesskette.

## Fazit

Business Central ist weder ein vollständig souveränes noch ein vollständig unsouveränes Produkt. Es ist ein kontrollierbarer ERP-Kern mit einer zunehmend cloudgebundenen Innovationsschicht.

Microsoft adressiert klassische Cloudrisiken inzwischen deutlich umfassender, als es manche Debatte vermuten lässt. Europäische Datenresidenz, Customer Managed Keys, Customer Lockbox, Identity Governance und Enterprise-Zusagen für AI reduzieren reale Risiken. Der CLOUD Act macht diese Maßnahmen nicht wertlos. Er erinnert aber daran, dass Datenresidenz und Rechtsraum nicht dasselbe sind.

An anderen Stellen setzt Microsoft auf offene Standards und Open Source. Damit bleiben Optionen erhalten: lokale Entwicklungswerkzeuge, alternative Modellprovider, eigene MCP-Schichten, externe AI-Agent-Plattformen und gemeinschaftlich gepflegte DevOps-Werkzeuge.

Andere Optionen sind deutlich schwerer zu spielen. Die Ausführung der tief integrierten AI-Agents bleibt Teil von Business Central Online. Bei der Telemetrie ist Azure Application Insights der produktisierte Standardpfad. Und auch GHE.com mit EU Data Residency ist keine europäische Plattform, sondern eine regionalisierte Betriebsoption eines US-Anbieters.

Die entscheidende Aufgabe ist nicht, Cloud und On-Premises gegeneinander auszuspielen. Wir müssen Schicht für Schicht entscheiden, welche Abhängigkeit bewusst akzeptiert wird, welche durch eine zweite Option abgesichert werden sollte und wo die strategische Bedeutung den Aufbau einer eigenen oder gemeinschaftlich getragenen Alternative rechtfertigt. Souveränität bedeutet nicht, möglichst wenige Abhängigkeiten zu haben. Sie bedeutet, die wichtigen Abhängigkeiten bewusst gewählt zu haben.

## Wer tiefer einsteigen möchte

Die wichtigsten Primärquellen und technischen Dokumentationen, auf denen die Einschätzung basiert:

**Business Central, Cloud und Governance**

- [Microsoft: Universal Code Initiative](https://www.microsoft.com/en-us/dynamics-365/blog/it-professional/2022/10/28/the-dynamics-365-business-central-universal-code-initiative-is-live/)
- [Microsoft: Änderung der On-Premises-Lizenzierung ab April 2025](https://techcommunity.microsoft.com/t5/business-applications-for/simplifying-licensing-across-our-smb-erp-solutions-don-t-miss/m-p/3808035)
- [Microsoft Learn: EU Data Boundary](https://learn.microsoft.com/en-us/privacy/eudb/eu-data-boundary-learn)
- [Microsoft Learn: Customer Managed Encryption Key für Business Central](https://learn.microsoft.com/en-us/dynamics365/business-central/admin-customer-managed-encryption-key)
- [Microsoft Learn: Customer Lockbox für Business Central](https://learn.microsoft.com/en-us/dynamics365/business-central/admin-customer-lockbox)
- [Microsoft: European Digital Commitments](https://blogs.microsoft.com/on-the-issues/2025/04/30/european-digital-commitments/)
- [Microsoft: Sovereign Cloud](https://blogs.microsoft.com/on-the-issues/2025/06/16/microsoft-sovereign-cloud/)
- [U.S. Congress: CLOUD Act](https://www.congress.gov/bill/115th-congress/house-bill/4943)
- [EDPB/EDPS: Auswirkungen des US CLOUD Act auf den europäischen Datenschutzrahmen](https://www.edpb.europa.eu/documents/edpb-correspondence/edpb-edps-joint-response-to-the-libe-committee-on-the-impact-of-the_en)

**AI, MCP und AI-Agents**

- [Microsoft Learn: Datenschutz und Datensicherheit für Copilot in Dynamics 365](https://learn.microsoft.com/en-us/dynamics365/faqs-copilot-data-security-privacy)
- [Microsoft Learn: Datenschutz für Azure Direct Models in Microsoft Foundry](https://learn.microsoft.com/en-us/azure/foundry/responsible-ai/openai/data-privacy)
- [Microsoft und Mistral: Erweiterte Partnerschaft für europäische AI-Infrastruktur und flexible Betriebsoptionen](https://www.prnewswire.com/in/news-releases/microsoft-and-mistral-expand-strategic-partnership-to-give-enterprises-and-regulated-industries-frontier-ai-they-can-control-302830228.html)
- [Microsoft Copilot Blog: Mistral Medium 3.5 in Copilot Studio](https://www.microsoft.com/en-us/microsoft-copilot/blog/copilot-studio/mistral-joins-copilot-studios-growing-lineup-of-model-providers/)
- [Microsoft Foundry: Mistral Document AI mit OCR 4 und Mistral Medium 3.5](https://techcommunity.microsoft.com/blog/azure-ai-foundry-blog/mistral-document-ai-with-ocr-4-and-mistral-medium-3-5-arrive-in-microsoft-foundr/4529863)
- [Microsoft Learn: Copilot- und Agentfunktionen in Business Central konfigurieren](https://learn.microsoft.com/en-us/dynamics365/business-central/enable-ai)
- [Microsoft Learn: Berechtigungen und Rollen des Payables Agent](https://learn.microsoft.com/en-us/dynamics365/business-central/payables-agent)
- [Microsoft Learn: Agent-Aktivitäten in Business Central überwachen](https://learn.microsoft.com/en-us/dynamics365/business-central/supervise-agent-tasks)
- [Microsoft Learn: AL MCP Server](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/developer/al-agent-tools/al-mcp-server)
- [Microsoft Learn: Business Central MCP Server](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/ai/configure-mcp-server)
- [Microsoft Learn: Admin Center MCP Server (Public Preview)](https://learn.microsoft.com/en-us/dynamics365/release-plan/2026wave1/smb/dynamics365-business-central/connect-ai-agents-admin-center-through-mcp-server)
- [Microsoft Learn: Agent SDK for AL](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/ai/ai-agent-sdk-overview)

**Entwicklung, Infrastruktur und Telemetrie**

- [Microsoft Learn: Business Central Telemetry](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-overview)
- [Microsoft Learn: Power-BI-Apps für Business-Central-Telemetrie](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-power-bi-app)
- [Microsoft Learn: Eigener Telemetrie-Ingestion-Endpoint](https://learn.microsoft.com/en-us/dynamics365/business-central/dev-itpro/administration/telemetry-control-cost#use-a-custom-endpoint)
- [GitHub Docs: Eigene Modellprovider und Offline-Modus in Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/customize-copilot/use-byok-models)
- [GitHub Docs: Enterprise Cloud with Data Residency](https://docs.github.com/en/enterprise-cloud@latest/admin/data-residency/about-github-enterprise-cloud-with-data-residency)
- [Freddy-DK AL-Go: GHE.com-Szenario](https://github.com/Freddy-DK/AL-Go/blob/main/Scenarios/UsingGitHubEnterprise.md)
- [Europäische Kommission: AI Factories und Gigafactories](https://commission.europa.eu/topics/competitiveness/ai-continent_en)
- [Microsoft: Ausbau der Rechenzentrumsinfrastruktur in Deutschland](https://news.microsoft.com/source/emea/2026/03/spatenstich-fuer-rechenzentrums-cluster-in-nordrhein-westfalen-microsoft-staerkt-die-digitale-infrastruktur-fuer-deutschlands-ki-zukunft/?lang=de)
- [Continue: Übernahme durch Cursor](https://www.continue.dev/)
- [SEC: Vereinbarte Übernahme von Anysphere durch SpaceX](https://www.sec.gov/Archives/edgar/data/1181412/000162828026043411/spaceexplorationtechnologi.htm)
