# walmart — Walmart Marketplace API skill

Skill mandiri (standalone) untuk
Walmart Marketplace API. Struktur identik dengan skill toolkit:

```
walmart/
├── SKILL.md          # name + description, workflow, output shape, references
├── agents/
│   └── openai.yaml   # interface config (display_name, short_description, default_prompt)
└── references/
    └── api/          # 17 kategori, 119 API doc (clean Markdown)
        ├── Item Management/
        ├── Price Management/
        ├── Order Management/
        ├── Inventory Management/
        └── ...
```

## Cara pakai (untuk agent/LLM)

Salin ke direktori skills coding-agent (mis. `.codex/skills/` atau
`.claude/skills/`), atau set langsung sebagai skill. Saat ada pertanyaan API Walmart,
skill `walmart-marketplace-api-guide` memandu inspect `references/api/**` lalu
cross-check ke dok resmi bila perlu.

## Update / regenerasi

Konten `references/api/` adalah **snapshot statis** dari OpenAPI specs yang di-download
community SDK `whitebox-co/walmart-marketplace-api` (`docs/schemas/`). Untuk memperbarui,
jalankan langkah download-schema SDK tersebut lalu toolchain di repo `updskills`:

```
python tools/spec_to_markdown.py \
  --spec walmart-sdk/docs/schemas \
  --outdir walmart/references/api
```

Tidak perlu mengedit manual satu-satu.
