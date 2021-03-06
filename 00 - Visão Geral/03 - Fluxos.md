---
title: Fluxos
---

Os serviços na Cartórios Tocantins seguem um fluxo padrão -- salvo excessões identificadas como tal. Esse fluxo é composto por uma fase inicial (Ponto de Partida) e outras 5 fases. No Ponto de Partida, as empresas pesquisam por cartórios que prestam serviços via API e se informam sobre quais serviços são prestados. Nas demais fases:

1. Autenticação: as informações de acesso são utilizadas para obter o Token JWT.
2. Registro de Serviço: o serviço é registrado e enviado diretamente do cliente para o cartório.
3. Orçamento e Pagamento: é criado o orçamento do serviço e disponibiilizado um link para pagamento.
4. Emissão de Exigência (Opcional): eventuais dados que não constem no pedido original podem ser solicitados por meio de uma exigência.
5. Relatório: O cartório informa metadados para a Cartórios Tocantins para fins de criação de estatísticas e indicadores.

Abaixo pode ser visto o detalhamento do fluxo em um diagrama. Cada um dos chamados é descrito com mais detalhes no link específico no menu lateral esquerdo.

![Fluxo](img/fluxo.svg)


