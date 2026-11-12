# Claude agent team

Een team van Claude Code-subagents voor agency-werk: een project manager die orkestreert en veertien specialisten.

## Installeren

Voor al je projecten, in je eigen Claude-map:

```bash
mkdir -p ~/.claude/agents && cp agents/*.md ~/.claude/agents/
```

Of alleen voor één project, zodat je collega's het team ook krijgen:

```bash
mkdir -p <project>/.claude/agents && cp agents/*.md <project>/.claude/agents/
```

## Gebruiken

Start een sessie met de project manager als hoofdagent:

```bash
claude --agent project-manager
```

De project manager stelt eerst vast wat je wilt ontvangen (advies, ontwerp of werkende software), kiest per vraag de kleinste set specialisten en laat elk document door een tweede specialist controleren.

## Het team

| Fase | Agent | Rol |
|---|---|---|
| Orkestratie | `project-manager` | Kiest het team, brieft, bewaakt volgorde en kwaliteit |
| Discovery | `solution-consultant` | Oplossingsrichting, scope, urenraming, adviesrapport |
| Discovery | `business-analyst` | Requirements en user stories; controleert rapporten tegen de vraag |
| Ontwerp | `ux-ui-designer` | Flows, schermen, componentspecificaties |
| Ontwerp | `software-architect` | Technische opties, ontwerp, taakverdeling |
| Bouw | `senior-developer-backend` | Server, API's, data, integraties |
| Bouw | `senior-developer-frontend` | UI, client-side state, styling |
| Bouw | `devops-engineer` | Pipelines, omgevingen, deployment, monitoring |
| Bouw | `content-specialist` | Teksten, contentstructuur, migratie, vertalingen |
| Bouw | `tracking-analytics-specialist` | Meetplan, datalayer, events, consent |
| Controle | `qa-engineer` | Tests en review tegen acceptatiecriteria |
| Controle | `security-privacy-reviewer` | Kwetsbaarheden, AVG, persoonsgegevens |
| Controle | `accessibility-specialist` | WCAG 2.2 AA |
| Controle | `seo-performance-specialist` | Technische SEO, migraties, Core Web Vitals |
| Oplevering | `technical-writer` | Documentatie, handleidingen, overdracht |

## Instellingen per agent

- **Denkniveau (`effort`):** `medium` voor de meeste rollen, `low` voor content, documentatie en tracking. De project manager volgt je sessie.
- **Model:** `content-specialist` en `technical-writer` draaien op Sonnet; de rest volgt het model van je sessie. Haal de regel `model: sonnet` weg om dat te veranderen.
- **Alleen de project manager orkestreert:** de specialisten mogen geen andere agents starten.

De prompts zijn stack-onafhankelijk en in het Engels; de agents antwoorden in de taal van de gebruiker.
