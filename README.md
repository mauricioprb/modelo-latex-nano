# Template de Dissertação/Tese - PPG em Nanociências (UFN)

Template LaTeX baseado no modelo em .docx do Programa de Pós-Graduação
em Nanociências da Universidade Franciscana (UFN) - Santa Maria, RS.

Em conformidade com as normas ABNT vigentes:

- **NBR 14724:2024** - Apresentação de trabalhos acadêmicos
- **NBR 10520:2023** - Citações em documentos
- **NBR 6023:2018** - Referências bibliográficas
- **NBR 6028:2021** - Resumo, resenha e recensão
- **NBR 6027:2012** - Sumário
- **NBR 6024:2012** - Numeração progressiva das seções

## Estilo visual

O template reproduz o modelo .docx do PPG:

- **Fonte:** Times New Roman 12 pt em todo o documento
- **Capa:** logo UFN no topo + cabeçalho institucional em negrito centralizado
- **Folha de rosto:** nome do autor no topo, título no centro, preâmbulo
  alinhado à direita, orientador e coorientador centralizados
- **Títulos de elementos pré-textuais** ("RESUMO", "LISTA DE FIGURAS",
  "SUMÁRIO" etc.) em CAIXA ALTA centralizados em negrito
- **Capítulos** ("1 INTRODUÇÃO") em negrito, alinhamento à esquerda,
  mesmo tamanho do corpo do texto
- **Seções e subseções** ("1.1 Objetivos", "1.1.1 Objetivo geral") em negrito,
  primeira letra maiúscula apenas, alinhamento à esquerda
- **Margens:** superior/esquerda 3 cm, inferior/direita 2 cm
- **Espaçamento:** 1,5 entre linhas no corpo, simples em citações longas
- **Recuo de primeira linha:** 1,25 cm

---

## Como usar no Overleaf (passo a passo)

### 1) Subir o template

1. Acesse [overleaf.com](https://www.overleaf.com) e faça login.
2. Clique em **New Project → Upload Project**.
3. Selecione este arquivo `.zip`.
4. Aguarde a página recarregar com o projeto aberto.

### 2) Configurar o compilador

1. No Overleaf, clique no menu **Menu** (canto superior esquerdo).
2. Em **Compiler**, selecione **pdfLaTeX**.
3. Em **Main document**, confirme que está apontando para `main.tex`.

### 3) Compilar pela primeira vez

1. Clique em **Recompile** (ou Ctrl + Enter).
2. Pode levar 1 a 2 minutos. Compile **duas vezes seguidas** para o sumário
   e as referências ficarem corretos.

### 4) Editar seus dados

Abra `main.tex` e procure pelo bloco **DADOS DO TRABALHO**. Preencha:

```latex
\titulo{Seu título aqui}
\autor{Seu Nome Completo}
\orientador{Prof. Dr. Nome do Orientador}
\coorientador{Prof. Dr. Nome do Coorientador}  % Apague se não houver
\data{2027}
```

### 5) Escrever os capítulos

Abra os arquivos dentro da pasta `capitulos/` e edite-os:

- `01-introducao.tex` - Introdução, objetivos, estrutura
- `02-fundamentacao.tex` - Revisão de literatura
- `03-metodologia.tex` - Materiais e métodos
- `04-resultados.tex` - Resultados e discussão
- `05-conclusoes.tex` - Conclusões e perspectivas

### 6) Adicionar referências

Abra `referencias.bib` e cole suas referências em formato **BibTeX**.

**Dica:** use **Zotero** ou **Mendeley** para exportar referências em BibTeX
automaticamente.

No texto, cite com:

```latex
\cite{rotulo2026}        % gera: (Autor, 2026)
\citeonline{rotulo2026}  % gera: Autor (2026)
```

### 7) Adicionar figuras

1. Coloque suas imagens na pasta `figuras/` (formatos: PNG, JPG, PDF).
2. Insira no texto com:

```latex
\begin{figure}[htb]
    \centering
    \caption{Sua legenda aqui.}
    \includegraphics[width=0.8\textwidth]{figuras/nome-do-arquivo}
    \label{fig:meu-rotulo}
    \fonte{Elaborado pelo autor.}
\end{figure}
```

---

## Estrutura do projeto

```
template-dissertacao-ufn/
├── main.tex                  ← Arquivo principal (CONFIGURAÇÕES E DADOS)
├── referencias.bib           ← Bibliografia (formato BibTeX)
├── README.md                 ← Este arquivo
│
├── elementos/                ← Partes pré-textuais
│   ├── 01-capa.tex                  (com logo UFN)
│   ├── 02-folha-rosto.tex
│   ├── 03-ficha-catalografica.tex   (placeholder; biblioteca emite o PDF)
│   ├── 04-folha-aprovacao.tex
│   ├── 05-dedicatoria.tex           (opcional)
│   ├── 06-agradecimentos.tex
│   ├── 07-epigrafe.tex              (opcional)
│   ├── 08-resumo.tex
│   ├── 09-abstract.tex
│   ├── 10-lista-figuras.tex         (gerada automaticamente)
│   ├── 11-lista-tabelas.tex         (gerada automaticamente)
│   ├── 12-lista-siglas.tex
│   └── 13-lista-simbolos.tex
│
├── capitulos/                ← Partes textuais
│   ├── 01-introducao.tex
│   ├── 02-fundamentacao.tex
│   ├── 03-metodologia.tex
│   ├── 04-resultados.tex
│   └── 05-conclusoes.tex
│
├── apendices/                ← Partes pós-textuais (opcionais)
│   ├── apendice-a.tex
│   └── apendice-b.tex
│
└── figuras/                  ← Imagens
    └── logo-ufn.png          (logo da Universidade Franciscana)
```

---

## Como citar no texto

| Você quer...                     | Comando                             | Saída                            |
| -------------------------------- | ----------------------------------- | -------------------------------- |
| Citação no final da frase        | `\cite{silva2026}`                  | `(Silva, 2026)`                  |
| Autor como sujeito da frase      | `\citeonline{silva2026}`            | `Silva (2026)`                   |
| Citação com página específica    | `\cite[p.~45]{silva2026}`           | `(Silva, 2026, p. 45)`           |
| Múltiplos trabalhos              | `\cite{silva2026,santos2023}`       | `(sILVA, 2026; Santos, 2023)`    |
| Citação direta longa (>3 linhas) | `\begin{citacao} ... \end{citacao}` | Recuo 4 cm, fonte menor, simples |

---

## Solução de problemas

### "Eu compilei e o sumário está vazio"

Normal na primeira compilação. **Compile duas vezes seguidas**.

### "As referências não aparecem"

Verifique se:

1. Você está citando as referências no texto com `\cite{...}`.
2. O rótulo do `\cite{...}` corresponde ao que está em `referencias.bib`.
3. Você compilou **duas vezes** depois de adicionar a citação.

### "Quero remover uma seção opcional (ex.: dedicatória)"

No `main.tex`, comente a linha correspondente adicionando `%` no início:

```latex
%\input{elementos/05-dedicatoria}
```

### "Quero trocar o logo da UFN"

Substitua o arquivo `figuras/logo-ufn.png` por outra imagem com o mesmo nome,
ou edite `elementos/01-capa.tex` apontando para o novo arquivo.

---

## Observações importantes

- **Ficha catalográfica:** é fornecida pela biblioteca da UFN. Apenas deixe
  a página reservada (já está no template) e substitua pelo PDF quando recebê-lo.
- **Folha de aprovação:** é assinada no dia da defesa. O template inclui uma
  versão "em branco"; troque pela versão oficial após a defesa.
- **CAPES:** se você teve bolsa CAPES, é **OBRIGATÓRIO** incluir o trecho
  de agradecimento padrão (já está no template).
- **Última palavra é da banca/orientador:** este template segue a ABNT e o
  modelo do PPG UFN, mas confirme com seu orientador antes de imprimir.

---

## Pacotes utilizados

- `abntex2` - classe para trabalhos ABNT
- `abntex2cite` - citações ABNT
- `mathptmx` - fonte Times New Roman para texto e matemática
- `helvet`, `courier` - fontes sans-serif e monoespaçada
- `graphicx`, `caption`, `subcaption` - figuras
- `amsmath`, `amssymb` - equações
- `chemformula` - fórmulas químicas
- `siunitx` - unidades do SI
- `booktabs`, `longtable`, `multirow` - tabelas
- `hyperref` - links no PDF
