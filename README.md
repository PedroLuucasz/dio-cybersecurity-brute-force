
# 🔐 Laboratório de Cibersegurança — DIO

## 📋 Sobre o projeto

Projeto prático de cibersegurança desenvolvido como parte de um desafio da DIO, com foco em testes de autenticação, enumeração de serviços, força bruta, Password Spraying e análise de mecanismos de proteção.

Todos os testes foram realizados em máquinas virtuais próprias, em um ambiente controlado e isolado.

## 🎯 Objetivos

- Configurar um laboratório virtual de segurança.
- Identificar portas e serviços disponíveis.
- Compreender ataques de força bruta.
- Demonstrar os riscos da reutilização de senhas.
- Analisar políticas de autenticação.
- Identificar medidas de prevenção.

## 🛠️ Ferramentas utilizadas

| Ferramenta | Finalidade |
|---|---|
| Kali Linux | Sistema operacional para testes |
| VirtualBox | Virtualização do laboratório |
| Metasploitable 2 | Máquina propositalmente vulnerável |
| Nmap 7.99 | Mapeamento de portas e serviços |
| Medusa 2.3 | Testes de autenticação |
| Enum4linux | Enumeração SMB |
| DVWA | Testes de segurança web |

## 🖥️ Configuração do ambiente

- Máquina de testes: Kali Linux.
- Máquina alvo: Metasploitable 2.
- Brute force web: DVWA.
- Rede de testes: Host-Only.
- IP do alvo: 192.168.56.102.

## 📡 Teste de conectividade

A comunicação entre as máquinas foi validada utilizando o comando:

```bash
ping -c 4 192.168.56.102
```

Resultados:

- 4 pacotes enviados.
- 4 pacotes recebidos.
- 0% de perda.
- Latência média de 18,428 ms.

## 🔎 Mapeamento de serviços

A varredura foi realizada utilizando o Nmap:

```bash
nmap -sV 192.168.56.102
```

Foram identificadas 23 portas TCP abertas e 977 fechadas.

| Porta | Serviço |
|---|---|
| 21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 80 | HTTP |
| 139 | NetBIOS |
| 445 | SMB |
| 3306 | MySQL |
| 5432 | PostgreSQL |

## 🔑 Teste de autenticação FTP

Foram utilizadas pequenas wordlists de laboratório para testar a autenticação FTP com o Medusa.

O teste identificou credenciais válidas, posteriormente verificadas por meio de uma conexão FTP.

Resultado: autenticação realizada com sucesso.

## 👥 Enumeração SMB

A ferramenta Enum4linux foi utilizada para identificar contas de usuários e consultar a política de senhas.

Foram observadas as seguintes fragilidades:

- Exposição de nomes de usuários.
- Complexidade de senhas desativada.
- Ausência de histórico de senhas.
- Ausência de limite de tentativas de autenticação.

As consultas apresentaram resultados divergentes sobre o tamanho mínimo de senha, indicando a necessidade de validação adicional.

## 🔓 Password Spraying

Foram criadas três contas fictícias exclusivamente para o laboratório:

- aluno01
- aluno02
- aluno03

As três contas foram configuradas com a mesma senha para demonstrar os riscos da reutilização de credenciais.

| Conta | Resultado |
|---|---|
| aluno01 | Sucesso |
| aluno02 | Sucesso |
| aluno03 | Sucesso |

Taxa de sucesso observada: 100%.

## 🌐 Teste de segurança web — DVWA

Foram realizados testes manuais de autenticação na aplicação DVWA, comparando os níveis de segurança Low e High.

| Característica | Low | High |
|---|---|---|
| Autenticação incorreta | Rejeitada | Rejeitada |
| Tempo de resposta | Rápido | Mais demorado |
| Resistência a tentativas repetidas | Menor | Maior |

No nível High, foi observado um atraso na resposta após uma tentativa incorreta.

O tempo exato não foi medido.

## 🛡️ Recomendações de segurança

- Utilizar senhas fortes e exclusivas.
- Implementar autenticação multifator quando disponível.
- Limitar tentativas de autenticação.
- Monitorar tentativas de acesso suspeitas.
- Restringir consultas SMB anônimas.
- Substituir FTP por protocolos seguros, como SFTP.
- Manter sistemas e serviços atualizados.
- Desativar serviços desnecessários.

## 📊 Resultados gerais

| Teste | Resultado |
|---|---|
| Conectividade | Concluído |
| Varredura Nmap | Concluído |
| Autenticação FTP | Concluído |
| Enumeração SMB | Concluído |
| Password Spraying | Concluído |
| Teste manual DVWA | Concluído |

## 📸 Evidências

As capturas de tela dos procedimentos e resultados serão disponibilizadas na pasta `imagens`.

## 📝 Conclusão

O desenvolvimento deste projeto permitiu aplicar conhecimentos práticos de cibersegurança, compreender vulnerabilidades relacionadas à autenticação e identificar os riscos associados às configurações inadequadas de serviços.

O laboratório também demonstrou a importância das políticas de senhas, do monitoramento de acessos e da implementação de mecanismos de proteção contra tentativas repetidas de autenticação.

## ⚠️ Aviso legal

Este projeto possui finalidade exclusivamente educacional. Todos os testes foram realizados em ambiente próprio, autorizado e isolado.

## 📚 Referências

- [DIO](https://www.dio.me/)
- [Kali Linux](https://www.kali.org/)
- [Nmap](https://nmap.org/)
- [Medusa](https://github.com/jmk-foofus/medusa)
- [DVWA](https://github.com/digininja/DVWA)

## 📄 Licença

Este projeto está sob a licença MIT.

## 👨‍💻 Autor

[PedroLuucasz](https://github.com/PedroLuucasz)
