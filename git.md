## Git

### Formato das mensagens de commit

Nós usamos o padrão usado pelo time do Angular como referência:

[https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#commits](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#commits)

### Trabalhando com branches

Dado que uma branch <nome_da_branch> está atrás da `master`, você pode seguir o seguinte processo, para atualizar ele com a master:

 1. Verifique se todas as mudanças feitas estão commitadas e que nada ficou no em `stash`;
 2. Faça um push para a branch remota: `git push origin <sua-branch>`
 3. Retorne a branch master: `git checkout master`
 4. Atualize a master: `git pull origin master`
 5. Volte para a sua branch: `git checkout <sua-branch>`
 6. Faça rebase da master: `git rebase master`
 7. Se conflitos aparecerem, resolva eles e então adicione as resoluções (`git add <arquivo-arrumado>`), e após resolver todos os conflitos continue o rebase (`git rebase --continue`)
 8. Após o rebase você agora precisa atualizar a sua branch remota: `git push -f` (sim `-f`, porquê após o rebase os seus commits tiveram seus hashes atualizados)
 9. Agora você pode finalmente criar o Pull Request (PR) e pegar um pouco de café.
