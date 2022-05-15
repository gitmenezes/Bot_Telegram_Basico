#### Bot básico para Telegram com pyTelegramBotAPI
[Biblioteca](https://pypi.org/project/pyTelegramBotAPI/#getting-started)

*Alexandre Menezes Ferreira*
> Telefone: 22-9-9822-9207


```python
#Instalação da biblioteca
!pip install pyTelegramBotAPI
```


```python
#Importação da Biblioteca
import telebot
```

### Criar Token Telegram
> Se você ainda não tem uma conta no telegram, baixe-o no seu celular e em seguida instale e siga os passos abaixo: 
* Vá em pesquisar e digite __BotFather__
* Acesse o botfather
* digite /newbot
* Escolha um nome para seu bot exemplo(__"meubot"__), a palavra bot tem que fazer parte do nome do seu bot, e este nome é único tal como um cpf.
* Em seguida escolha um nome de usuário para o bot, também necessita da palavra __bot__ no nome escolhido
* Feito tudo isso, anote seu Token e lembre-se ele deve ser secreto!
>> 


```python
#Próssimo passo
#Definir a variável Token
token = "seu toquem aqui"
```


```python
#Start do bot com seu token
bot =  telebot.TeleBot(token)#token = token que você criou e atribuiu a variável
```

#### Mensagem padrão para quando o Bot iniciar


```python
#Vamos criar agora a estrutura do bot
#boas vindas
@bot.message_handler(commands=['start'])#Decorador que inicia o Bot
def Mensagm_de_boas_vindas(message):
    bot.reply_to(message, "Olá, todos são bem vindos!")
```


```python
#Coletor de mensagens recebidas no bot
def Todas_as_mensagens(msg):
    return True
```


```python
@bot.message_handler(func=Todas_as_mensagens)
def handle_text_doc(message):
    if message.text == "oi": #Cliente diz
        bot.reply_to(message,"Em que posso ajudar?")#Bot Responde
    if message.text == "Olá": #Cliente diz
        bot.reply_to(message,"Seja bem vindo(a)")#Bot Responde
    if message.text == "Oie": # Cliente diz
        bot.reply_to(message,"Saudações")#Bot Responde
    if message.text == "iae": # Cliente diz
        bot.reply_to(message,"Blz, posso ajudar?") #Bot Responde

```


```python
# Este é o fechamento do código, com ele seu código responderá infinitamente ao Bot
bot.infinity_polling()
```

#### [Manifesto para Desenvolvimento Ágil de Software](https://agilemanifesto.org/iso/ptbr/manifesto.html)



_Estamos descobrindo maneiras melhores de desenvolver
software, fazendo-o nós mesmos e ajudando outros a
fazerem o mesmo. Através deste trabalho, passamos a valorizar:_

_Indivíduos e interações mais que processos e ferramentas
Software em funcionamento mais que documentação abrangente
Colaboração com o cliente mais que negociação de contratos
Responder a mudanças mais que seguir um plano_

_Ou seja, mesmo havendo valor nos itens à direita,
valorizamos mais os itens à esquerda._
