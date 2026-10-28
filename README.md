# Compressor de PDF

Interface web para reduzir PDFs pesados sem depender do Adobe Acrobat nem de sites externos. Roda na rede interna: qualquer colega abre pelo navegador, sem instalar nada.

> **Estudo de caso.** O código é de uso interno de uma empresa e fica em um repositório privado.

## O problema

Catálogos e revistas em PDF chegam a centenas de megabytes e travam o envio por e-mail e o upload. Enviar arquivos da empresa para sites de compressão da internet também não é uma opção.

## O que faz

- Comprime PDFs grandes (em testes, a redução chegou a até 96%, dependendo do conteúdo).
- Três níveis de compressão, para escolher entre qualidade e tamanho:

| Nível | Resolução | Qualidade JPEG | Uso recomendado |
| --- | --- | --- | --- |
| Alta | 150 DPI | 75% | Documentos com texto fino |
| Média | 100 DPI | 65% | Revistas e catálogos (padrão) |
| Máxima | 72 DPI | 50% | Maior redução de tamanho |

- **Privacidade.** Os arquivos não são salvos no servidor: são processados em memória e descartados depois do download.
- **Acesso pela rede.** Um servidor em uma máquina da rede atende todos os colegas.

## Arquitetura

Servidor **Flask** (Python) com uma única página web. O PDF é recebido, as imagens internas são reamostradas e recomprimidas no nível escolhido, e o resultado volta como download.

## Minha parte

Construí a ferramenta inteira: servidor, lógica de compressão, interface e instruções de instalação para o time.

## Tecnologias

Python · Flask · HTML · CSS · JavaScript

## Contato

Pedro Rodrigues da Cunha · [LinkedIn](https://www.linkedin.com/in/pedrorodrigues2) · [GitHub](https://github.com/rodriguespedro22)
