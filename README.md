# Citizen Assist AI – Energia e Sustentabilidade
**Global Solution – Soluções em Energias Renováveis e Sustentáveis | Ciência da Computação (1CC)**

## 1. Integrantes
| Nome completo | RM |
|---|---|
| Leonardo Fortini | 572566 |
| Mauricio Bertucci | 571229 |

## 2. Público e problema
O assistente atende **famílias que usam chuveiro elétrico** e querem reduzir a conta de luz. O chuveiro é um dos equipamentos de maior potência da casa e muita gente não sabe quanto ele pesa na conta nem quais alternativas existem. O assistente explica isso em linguagem simples, com números, fontes e avisos sobre as limitações.

## 3. Funcionalidades de energia
- **Calculadora de consumo:** informa potência, minutos de banho e moradores e recebe kWh/mês e custo em R$, usando a tarifa real da distribuidora (ANEEL).
- **Comparador de alternativas:** banho mais curto x aquecedor solar (fonte renovável), com economia, investimento, retorno e CO₂ evitado.
- **Recomendação:** sugere a opção conforme o perfil (imóvel alugado x casa própria).
- **Transparência:** toda resposta traz fontes e o aviso de que os valores são estimativas.
- **Perguntas livres:** "quanto gasto com meu chuveiro?", "vale a pena aquecedor solar?".

## 4. Como executar e testar
```bash
git clone https://github.com/[usuario]/[repositorio].git
cd [repositorio]
python energia/calculos/comparacao.py
python energia/assistente/modulo_energia.py
```
Não precisa instalar bibliotecas (Python 3.8+). Teste sugerido: na opção 1 do menu, aperte Enter em todas as perguntas (valores padrão) e confira **88 kWh/mês**.

## 5. Contribuição de Energias Renováveis
Tudo da disciplina está em [`/energia`](./energia): dados, cálculos, justificativas, referências e testes. Veja [`energia/README_energia.md`](./energia/README_energia.md).

## 6. De onde vêm os dados
| Dado | Tipo | Origem |
|---|---|---|
| Tarifa residencial (TUSD + TE) por distribuidora | **Real** | ANEEL, Tarifas Homologadas (dados abertos), arquivo gerado em 13/11/2026 |
| Fator de emissão de CO₂ (0,0385 kg/kWh) | **Real** | MCTI, média anual do SIN em 2023 |
| Fração solar (70%) | **Baseado em estudo** | UFRGS/Ambiente Construído; IFPB/Principia |
| Potência, tempo de banho, nº de moradores | Estimado | Cenário padrão, alterável no assistente |
| Custo do aquecedor solar (R$ 4.500), manutenção, vida útil | Estimado | A substituir por orçamento real |
| Impostos (25%) | Estimado | A tarifa da ANEEL não inclui impostos |

Detalhes e justificativas em [`energia/dados/premissas.md`](./energia/dados/premissas.md).

## 7. Resultado do cenário padrão
Enel SP (nome no arquivo da ANEEL: ELETROPAULO), chuveiro de 5.500 W, 8 min por banho, 4 moradores. Tabela completa em [`energia/calculos/comparacao.md`](./energia/calculos/comparacao.md). **São estimativas, não garantia de economia.**

## 8. Limitações
- Não inclui bandeira tarifária nem tarifa social (baixa renda).
- Não considera reajustes de tarifa nem inflação ao longo dos anos.
- Emissões da fabricação do aquecedor solar não foram consideradas.
- O desempenho do aquecedor solar varia com clima, orientação do telhado e tamanho do sistema (estudos encontraram frações solares de 48% a 88%).

## 9. Referências
1. ANEEL. Tarifas Homologadas das Distribuidoras de Energia Elétrica. https://dadosabertos.aneel.gov.br/
2. MCTI. Fator de emissão de CO₂ na geração de energia elétrica no Brasil em 2023. https://www.gov.br/mcti/pt-br/acompanhe-o-mcti/noticias/2024/02/fator-de-emissao-de-co2-na-geracao-de-energia-eletrica-no-brasil-em-2023-e-o-menor-em-12-anos
3. MCTI. Nota técnica (jun/2025) sobre os fatores de emissão do SIN. https://cenarioenergia.com.br/wp-content/uploads/2025/06/NT_FE_jun25.pdf
4. UFRGS, Ambiente Construído. Sistema solar térmico com apoio elétrico x chuveiro elétrico. https://seer.ufrgs.br/ambienteconstruido/article/download/25706/21162
5. IFPB, Principia. Análise técnica e econômica de aquecimento solar de água. https://periodicos.ifpb.edu.br/index.php/principia/article/download/145/115
6. Unicamp, BTSym 2021. Aquecedores de água residenciais. https://lcv.fee.unicamp.br/wp-content/images/BTSym-21/papers/BTSym2021_011_v1.pdf
7. Idec. Economia com aquecedor solar. https://idec.org.br/dicas-e-direitos/economia-com-aquecedor-solar
8. Idec. Como funciona um aquecedor de água solar. https://idec.org.br/dicas-e-direitos/como-funciona-um-aquecedor-de-agua-solar
9. EPE, Anuário Estatístico (citado pelo Canal Solar). https://canalsolar.com.br/emissoes-de-co%e2%82%82-geracao-eletrica-mcti/

Lista completa com descrição em [`energia/referencias.md`](./energia/referencias.md).

## 10. Testes com usuários
Registros e ajustes em [`energia/testes_usuarios/registro_testes.md`](./energia/testes_usuarios/registro_testes.md).
