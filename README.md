# dslist

## Deploy
configure essas variaveis de ambiente:
APP_PROFILE = prod
DB_URL (Formato: jdbc:postgresql://host:porta/nomedabase)
DB_USERNAME
DB_PASSWORD
CORS_ORIGINS = (hosts com acesso autorizado!)

## TESTE
Dentro do h2-console use esse comando e dê RUN:
SELECT TB_BELONGING .*, TB_GAME.TITLE FROM TB_BELONGING INNER JOIN TB_GAME ON TB_GAME.ID = TB_BELONGING.GAME_ID 
WHERE LIST_ID = 2 
ORDER BY POSITION

agora no Postman use dê um POST no endereço:
http://localhost:8080/list/2/replacement

antes de dar o POST vá em (Body), marque a opção (raw) e coloque esse código JSON:
{
    "sourceIndex": 3,
    "destinationIndex": 1
}

Agora o jogo Cuphead mudou da position 3 para a 1 e empurrou os outros jogos que estavam abaixo da posição 1 até a posição 3 em que ele saiu.
