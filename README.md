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