# Changelog — Documentos Legais do PegadaFit

Mantém histórico das versões dos Termos, Privacidade, Uso Aceitável, Disclaimer e Cancelamento.

Formato: [Keep a Changelog](https://keepachangelog.com/pt-BR/1.1.0/) + [SemVer](https://semver.org/lang/pt-BR/).

Quando atualizar:
- **MAJOR (X.0.0)** — mudança estrutural ou de princípio que exige re-aceite e comunicação ativa
- **MINOR (1.X.0)** — esclarecimento ou inclusão que não muda direitos/obrigações de forma material
- **PATCH (1.0.X)** — correção de erro de redação, link quebrado, atualização de endereço

---

## [2.1.0] — 2026-05-17 (Termos de Uso)

### Adicionado
- **Seção 3 (Quem pode usar):** novas regras de antifraude/duplicação
  - 1 conta por aparelho a cada 30 dias (cooldown de device)
  - Email descartável (Mailinator, TempMail, etc) bloqueado
  - Email canônico: Gmail/Googlemail ignora aliases `+` e pontos
  - DDD válido obrigatório (lista ANATEL)
  - Telefone único: mesmo número não usável em duas contas
- **Seção 5 (Conteúdo):** subseções novas
  - **5.1 Limites técnicos** de conteúdo:
    - Vídeo no Feed: até 30s, 25MB
    - Foto Feed: até 15MB, carrossel max 10 fotos
    - Áudio DM/Salão: até 5min
    - Stories: até 15s vídeo, expira em 24h
  - **5.2 Moderação:** shadowban, suspensão e banimento podem ocorrer com base em denúncia ou revisão da nossa equipe. Casos graves (CSAM, ameaça) reportados a PF/SaferNet.
- **Seção 7-A NOVA (Fit/Match):**
  - Foto obrigatória pra ambos lados (caller + target)
  - Conta institucional (academia/empresa/time) não participa
  - Match exige idade ≥ 18 dos 2 lados

### Motivo
Atualização técnica do app (migs 388/390/393) introduziu defesas anti-conta-falsa,
limites técnicos de vídeo e gate de foto pra Fit. Termos precisavam refletir.

### Re-aceite
- TERMS_VERSION bumpado `2.0 → 2.1` no app
- `ReaceiteScreen` exibe automaticamente pra todo user ativo na próxima abertura
- Política de Privacidade, Uso Aceitável, Disclaimer Médico e Cancelamento **não mudaram materialmente** — permanecem como antes

---

## [1.0.0] — 2026-04-25

### Adicionado
- Versão inicial dos 5 documentos legais:
  - Termos de Uso
  - Política de Privacidade
  - Política de Uso Aceitável
  - Disclaimer Médico
  - Política de Cancelamento e Eliminação de Dados
- Atribuições CC BY 4.0 ao Basecamp (templates originais)
- Modelo de Vitrine: **vitrine + chat, pagamento off-platform** (modelo B)
- Idade mínima: **18 anos**
- Foro de eleição: Comarca de Castanhal/PA
- Controlador: Valdenor Neto (pessoa física), Castanhal/PA
- DPO: dpo@pegadafit.com
