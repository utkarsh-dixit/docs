---
title: 'Configurar a Firewall Network'
excerpt: 'Saiba como configurar a Firewall Network'
slug: firewall-network
section: 'Redes & IP'
---

> [!primary]
> Esta tradução foi automaticamente gerada pelo nosso parceiro SYSTRAN. Em certos casos, poderão ocorrer formulações imprecisas, como por exemplo nomes de botões ou detalhes técnicos. Recomendamos que consulte a versão inglesa ou francesa do manual, caso tenha alguma dúvida. Se nos quiser ajudar a melhorar esta tradução, clique em "Contribuir" nesta página.
>

**Última atualização: 23/12/2021**

## Sumário

Para proteger a sua infraestrutura geral e os servidores dos seus clientes, a OVHcloud propõe uma firewall com várias opções de configuração integrada na solução **Anti-DDoS**: a Firewall Network. Esta opção permite limitar a exposição dos serviços aos ataques provenientes da rede pública.

**Este manual explica como configurar a Firewall Network.**


> [!primary]
>
> Para obter mais informações sobre a nossa solução Anti-DDoS, consulte a página: <https://www.ovh.pt/anti-ddos/>.
> 

![ Tudo sobre o sistema VAC](images/vac-inside.png){.thumbnail}


## Requisitos

- Dispor de um serviço OVHcloud com Firewall Network incluída: [servidor dedicado](https://www.ovh.pt/servidores_dedicados/){.external}, [VPS](https://www.ovh.pt/vps/){.external}, [instância Public Cloud](https://www.ovh.pt/public-cloud/instances/){.external}, [Private Cloud](https://www.ovh.pt/private-cloud/){.external}, [IP Failover](https://www.ovh.pt/servidores_dedicados/ip_failover.xml){.external}, etc.
- Ter acesso à [Área de Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pt/&ovhSubsidiary=pt){.external}.


## Instruções

### Ativar a Firewall Network

> [!primary]
>
> A Firewall Network foi concebida para proteger os endereços de IP associados a uma máquina. Cada IP deverá ser configurado de forma independente. Não é possível realizar uma configuração simultânea dos IP do servidor.
> 

Depois de aceder à [Área de Cliente OVHcloud](https://www.ovh.com/auth/?action=gotomanager&from=https://www.ovh.pt/&ovhSubsidiary=pt){.external}, aceda ao menu `Bare Metal Cloud`{.action} e clique na secção `IP`{.action} na barra lateral esquerda. Clique em `...`{.action} para ativar a firewall no IPv4 pretendido.

![Ativação da Firewall Network](images/firewall_creation.png){.thumbnail}

É-lhe solicitada uma confirmação.

![Validação](images/creationvalid.png){.thumbnail}

Em seguida, clique em `Ativar a firewall`{.action} (1) e selecione a opção `Configurar a Firewall`{.action} (2) para iniciar a configuração.

![Ativação da configuração ](images/activationconfig.png){.thumbnail}

Pode definir até **20 regras para cada IP**.

> [!warning]
>
> A firewall é ativada automaticamente sempre que houver um ataque DDoS, só podendo ser desativada depois de o ataque ter terminado. Por isso, é necessário manter as definições da firewall sempre atualizadas.
> Por predefinição, o serviço não tem qualquer regra definida, por isso todas as ligações são permitidas.
> Se possuir alguma, verifique-as regularmente mesmo se desativar a firewall.
> 


> [!primary]
>
> - A fragmentação UDP está bloqueada por predefinição (DROP). Após a ativação da Firewall Network, e se usar uma VPN, deverá configurar corretamente a maximum transmission unit (MTU). Por exemplo, em OpenVPN, pode selecionar `MTU test`{.action}.
> - A Firewall Network não produz efeitos dentro da rede OVHcloud. Ou seja, as regras implementadas não irão afetar as ligações dentro da rede OVHcloud.
>


### Configurar a Firewall Network

Adicione uma regra através da opção  `Adicionar uma regra`{.action}.

![Adicionar uma regra](images/ajoutregle1.png){.thumbnail}

Para cada regra, deve selecionar:

- o nível de prioridade (de 0 a 19, sendo que é aplicada a primeira regra);
- uma ação (`Autorizar`{.action} ou `Recusar`{.action});
- o protocolo;
- um IP (opcional);
- a porta de origem (apenas TCP);
- a porta de destino (apenas TCP);
- as opções TCP (apenas TCP).

![Como adicionar uma regra](images/ajoutregle4.png){.thumbnail}


> [!primary]
>
> - Prioridade 0: é aconselhável autorizar o protocolo TCP para todos os IP com uma opção `established`{.action}. Esta opção permite verificar se o pacote faz parte de uma sessão já iniciada. Se não der autorização, o servidor não irá receber as respostas do protocolo TCP aos pedidos de ligação (requests) SYN/ACK.
> - Prioridade 19: se não tiver sido definida nenhuma regra com prioridade inferior a 19 (a última possível), os protocolos para IPv4 serão todos recusados.
> 

### Exemplo de configuração

Para garantir que só ficarão abertas as portas SSH (22), HTTP (80), HTTPS (443) e UDP (10000) ao autorizar o ICMP, é necessário seguir as seguintes regras:

![Exemplo de configuração](images/exemple.png){.thumbnail}

As regras são ordenadas sequencialmente de 0 (primeira regra lida) a 19 (última regra lida). A sequência de leitura é interrompida a partir do momento em que uma regra é aplicada ao pacote recebido.

Por exemplo, um pacote destinado à porta 80/TCP é identificado pela regra 2 e esta é executada. As regras seguintes já não serão acionadas. Um pacote destinado à porta 25/TCP só poderá ser identificado pela última regra (19), e será bloqueado. Nas regras precedentes, a OVHcloud não autoriza qualquer comunicação na porta 25.

> [!warning]
>
> Em caso de ativação da mitigação Anti-DDoS, as regras da Firewall Network serão ativadas, mesmo tendo sido desativadas anteriormente. Se optar  pela desativação, não se esqueça de eliminar as regras.
> 

### Configurar a firewall Armor (Firewall Game)

> [!primary]
> Por predefinição, a firewall Armor está pré-configurada com certas regras que a OVHcloud determinou funcionar com os jogos mais comuns. No entanto, para os clientes que disponham de um servidor dedicado Game, permitimos-lhe ir mais longe e configurar igualmente regras para as portas.
>

Para configurar as regras das suas portas no Armor, primeiro tem de aceder à Área de Cliente OVHcloud.<br>
De seguida, aceda ao menu `Bare Metal Cloud`{.action} e clique na secção `IP`{.action} na barra lateral esquerda. Clique em `...`{.action} junto do endereço IP do seu servidor de jogo e, a seguir, em `Configurar a Firewall Game`{.action}.

![Game_wall](images/GAMEwall2021.png){.thumbnail}

No ecrã seguinte, clique no botão `Adicionar uma regra`{.action} para adicionar uma regra ao Armor.

![Configura_Armor](images/ConfigureArmor2021.png){.thumbnail}

Ative as portas conforme as suas necessidades no ecrã seguinte e clique no botão `Confirmar`{.action} quando acabou de adicionar as suas regras. A firewall Armor foi configurada com sucesso.

## Quer saber mais?

Fale com a nossa comunidade de utilizadores <https://community.ovh.com/en/>.