# Perguntas para Destrava Dev

1. Como fazer o catch ser executado?
2. O ideal é posicionar esse try/catch dentro do callback que lida com a mudança de estado (`handleAuthStateChanged`) em um momento em que tanto faz se o usuário está logado ou deslogado?

---

# 1

Olá pessoal, tudo bom? Feliz dia das crianças =D

Gostaria de tirar uma dúvida que tenho sobre o Firebase.

No trecho de código abaixo, a função `handleAuthStateChanged` é o callback que lida com a mudança do estado de autenticação do usuário na aplicação. 

Logo no início dela, eu coloquei um try/catch que executa o redirect da autenticação pelo Google. 

A minha dúvida é: como fazer o catch ser executado?

```javascript
const handleAuthStateChanged = async user => {
  try {
    const result = await getRedirectResult(auth)
    console.log('result:', result)
  } catch (error) {
    console.log('error at getRedirectResult function:', error)
  }

  // ...
}
```

[Nessa página](https://firebase.google.com/docs/reference/js/auth#getredirectresult) da documentação mostra como a `getRedirectResult` funciona, mas não mostra como tratar erros caso o redirect falhe...
