# teste-ammend-force

Teste para ammend com push forçado.

## Passos do teste

1. Criar repositório.
2. Efetuar uma série de commits (3 ou 4).
3. Efetuar um commit com mensagem "errada".
4. Efetuar mais um ou dois commits e efetuar push.
5. Efetuar Push para servidor.
6. Efetuar checkout para a revisão da mensagem errada.
7. Efetuar ammend (git commit --ammend -m "nova mensagem") para trocar a mensagem.
8. Checar historico.
9. Efetuar Push forçado (git push --force).
10. Checar:
    1. Se somente a mensagem desejada foi modificada.
    2. Se não foi perdido nenhum commit após o force.
    3. Se não foi gerado problema no commit além da mensagem.

## Acima não rolou, teste 2, usando fixup

1. Levantar hash do commit
2. No branch escrever:
    1. (git commit --fixup=reword:<commit-hash> -m "Mensagem a ser trocada")

## Acima não rolou, teste 3, usando rebase

1. Levantar o hash do commit
2. git rebase -i <commit-hash>~1 (repare no ~1, que pega o commit anterior)
3. Será aberto um editor de texto. Mude de `pick` para `reword` o commit com a mensagem incorreta. Salve o arquivo e feche o editor.
    1. O editor de texto vai abrir de novo no commit que você colocou `reword`. Corrija a mensagem! Salve o arquivo e feche o editor.
4. Será efetuada atualização de cada commit da sequência e ao final é necessário dar um `git push --force`

**Funciona, mas é arriscado**

## ainda não rolou, teste 4, --force-with-lease

1. Levantar o hash do commit
2. git rebase -i <commit-hash>~1 (repare no ~1, que pega o commit anterior)
3. Será aberto um editor de texto. Mude de `pick` para `reword` o commit com a mensagem incorreta. Salve o arquivo e feche o editor.
    1. O editor de texto vai abrir de novo no commit que você colocou `reword`. Corrija a mensagem! Salve o arquivo e feche o editor.
4. Será efetuada atualização de cada commit da sequência e ao final é necessário dar um `git push --force-with-lease`, pq se o git identificar algum commit após ele irá abortar a operação.

* Mais info: <https://www.educative.io/edpresso/how-to-change-a-git-commit-message-after-a-push>
