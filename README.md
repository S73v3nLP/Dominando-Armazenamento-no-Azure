## Dominando-Armazenamento-no-Azure
### Lab do Curso AZ900 da DIO.me - Criação de Storage Account, Migration e uso do AzCopy

# Criando uma _Storage Account_

🔹 Ao criar uma nova Storage Account no portal Azure, o tipo **StorageV2 (com suporte a blobs)** é exibido como padrão.  
🔹 Essa configuração reflete a recomendação da Microsoft desde 2020 para cenários gerais.  
🔹 O destaque ao Blob Storage ocorre devido à sua ampla adoção em aplicações modernas.


1. No menu esquerdo do portal, selecione _Storage Account_ para exibir uma lista das contas de armazenamento. Se o menu do portal não estiver visível, selecione o botão de menu para ativá-lo.
  <img width="831" height="836" alt="Image" src="https://github.com/user-attachments/assets/e7667d43-587e-4a04-b84c-c990e11e8c08" />

2. Na página Contas de armazenamento, clique em _Create_.
<img width="904" height="656" alt="Image" src="https://github.com/user-attachments/assets/ba01a9a7-fa22-44e3-b494-316c2b982a57" />

3. Na guia _Basics_, forneça as informações essenciais para a sua conta de armazenamento. A imagem a seguir mostra uma configuração padrão com as propriedades básicas de uma nova _Storage Account_. Clique em _Next_
<img width="884" height="879" alt="Image" src="https://github.com/user-attachments/assets/000c3130-3a65-43a6-ac48-5d3fc95b9deb" />

4. Em _Advanced_ deixa as opções como padrão
5. Guia _Networking_ também toda _default_
6. Na guia _Data Protection_, foram desmarcadas todas as flags de proteção por conta de laboratóroio para produção pode ser deixado habilitado.
  <img width="855" height="904" alt="image" src="https://github.com/user-attachments/assets/32824fc6-ae66-415f-8c04-66cd55c024b5" />

7. Na guia _Encryption_ deixar tudo no padrão.
8. Clicar em _Review + Create_
9. Após a validação clicar em _Create_
<img width="883" height="923" alt="image" src="https://github.com/user-attachments/assets/e5b2995e-bcac-47bc-9084-ba6d7d9c9a5d" />

10. _Storage Account_ criada:
  <img width="1151" height="588" alt="image" src="https://github.com/user-attachments/assets/0dc3da6d-31e9-46c5-ba7a-424832c7b089" />

# Utilizando **AzCopy** para copiar dados de uma fonte local para uma conta de armazenamento do Azure

## AzCopy é um utilitário de linha de comando que você pode usar para copiar blobs ou arquivos de ou para uma conta de armazenamento. 

1. Baixe e execute o AzCopy
  <img width="875" height="436" alt="image" src="https://github.com/user-attachments/assets/2591fbf9-47e9-4b4d-ad91-45a0305c0223" />


2. Como boa prática salve o arquivo em uma pasta exclusiva para o AzCopy
3. Vamos usar a opção de fornecer um **TOKEN SAS** para cada URL de origem
   ```
   http://<storage-account-name>.blob.core.windows.net/<container-name><SAS-token>
  
## Carregar arquivos no Armazenamento de Blobs do Azure usando o AzCopy

1. No portal do Azure vá em _Storage Accounts_ 
  <img width="1191" height="701" alt="image" src="https://github.com/user-attachments/assets/2eb9d87f-716e-49c4-b163-f25c9ed01658" />

2. clique na _Storage Account_ que pretende utilizar
  <img width="1132" height="543" alt="image" src="https://github.com/user-attachments/assets/f3626384-975d-4dfe-a25c-020855814668" />

3. Clique em _Containers_ e acesse o seu. Caso não tenha um, crie
4. Clique em _Shared Acces Tokens_
  <img width="1161" height="743" alt="image" src="https://github.com/user-attachments/assets/7916f454-42fa-43b7-8eb5-924f4a7d04da" />

5. Agora vá em _Permissions_ e habilite todas
  <img width="936" height="715" alt="image" src="https://github.com/user-attachments/assets/a5a7703f-7d45-43d9-9b35-5aedfc7b0177" />

6. Clique em _Generate SAS token and URL_
  
7. Copie o código que está em _Blob SAS URL_
  <img width="1601" height="809" alt="image" src="https://github.com/user-attachments/assets/ade0697b-300a-4416-b610-67a476a44f28" />

8. Em sua máquina local abra o CMD e vá para a pasta aonde oexecutável do AzCopy está guardado:
    <img width="1316" height="697" alt="image" src="https://github.com/user-attachments/assets/849c1a1e-b682-40ea-bd14-015942b50241" />

9. Execute o comando
   Azcopy copy "C:\copia" <URL SAS criada> --recursive=true
10. Ao final ele informa quantos arquivos e se ocorreu tudo bem
  <img width="1503" height="875" alt="image" src="https://github.com/user-attachments/assets/570a17b8-3ed2-41fe-b36e-71f3125068da" />

  <img width="1394" height="627" alt="image" src="https://github.com/user-attachments/assets/eafbc9ba-4a30-4ce3-b584-09eaef82f7e2" />




