# Guia para Adicionar Imagens ao Sistema de Terços

## Problema Identificado
Seu sistema está configurado para usar imagens, mas a maioria dos produtos não tem imagens associadas, apenas emojis como fallback.

## Estrutura de Pastas Recomendada

```
Encantus/
├── img/
│   ├── logo.png (já existe)
│   ├── pulso/
│   │   ├── imgpulsosb1.png (já existe)
│   │   ├── sao-bento-2.png
│   │   ├── aparecida-pulso-1.png
│   │   └── ...
│   ├── tradicional/
│   ├── chaveiro/
│   ├── veiculo/
│   ├── noiva/
│   ├── luxo/
│   ├── infantil/
│   └── embalagem/
```

## Como Adicionar Imagens

### 1. Organize as Imagens
- Coloque as imagens na pasta `img/` com nomes descritivos
- Use formato `.jpg` ou `.png`
- Tamanho recomendado: 300x300px ou 400x400px
- Mantenha a proporção consistente

### 2. Atualize o Código

#### Método A - Adicionar imagem individual:
```javascript
// Substitua:
"São Bento": gerarItens("São Bento Pulso", 5, 35, '✝️'),

// Por:
"São Bento": [
  { nome: "São Bento Pulso 1", preco: 35, img: "img/pulso/sao-bento-1.png", emoji: '✝️' },
  { nome: "São Bento Pulso 2", preco: 35, img: "img/pulso/sao-bento-2.png", emoji: '✝️' },
  ...gerarItens("São Bento Pulso", 3, 35, '✝️')
],
```

#### Método B - Adicionar todas as imagens de uma categoria:
```javascript
"São Bento": [
  { nome: "São Bento Pulso 1", preco: 35, img: "img/pulso/sao-bento-1.png", emoji: '✝️' },
  { nome: "São Bento Pulso 2", preco: 35, img: "img/pulso/sao-bento-2.png", emoji: '✝️' },
  { nome: "São Bento Pulso 3", preco: 35, img: "img/pulso/sao-bento-3.png", emoji: '✝️' },
  { nome: "São Bento Pulso 4", preco: 35, img: "img/pulso/sao-bento-4.png", emoji: '✝️' },
  { nome: "São Bento Pulso 5", preco: 35, img: "img/pulso/sao-bento-5.png", emoji: '✝️' }
],
```

### 3. Sistema de Fallback
O sistema já tem fallback automático:
- Se a imagem existir → mostra a imagem
- Se a imagem não carregar → mostra o emoji
- Se não há imagem → mostra o emoji

## Exemplo Prático

### Antes (apenas emojis):
```javascript
pulso: {
  "São Bento": gerarItens("São Bento Pulso", 5, 35, '✝️'),
  "Aparecida": gerarItens("Aparecida Pulso", 5, 35, '🕊️')
}
```

### Depois (com imagens):
```javascript
pulso: {
  "São Bento": [
    { nome: "São Bento Pulso 1", preco: 35, img: "img/pulso/sao-bento-1.png", emoji: '✝️' },
    { nome: "São Bento Pulso 2", preco: 35, img: "img/pulso/sao-bento-2.png", emoji: '✝️' },
    { nome: "São Bento Pulso 3", preco: 35, img: "img/pulso/sao-bento-3.png", emoji: '✝️' },
    { nome: "São Bento Pulso 4", preco: 35, img: "img/pulso/sao-bento-4.png", emoji: '✝️' },
    { nome: "São Bento Pulso 5", preco: 35, img: "img/pulso/sao-bento-5.png", emoji: '✝️' }
  ],
  "Aparecida": [
    { nome: "Aparecida Pulso 1", preco: 35, img: "img/pulso/aparecida-1.png", emoji: '🕊️' },
    { nome: "Aparecida Pulso 2", preco: 35, img: "img/pulso/aparecida-2.png", emoji: '🕊️' }
  ]
}
```

## Passos para Implementar

1. **Crie as pastas necessárias** dentro de `img/`
2. **Adicione as imagens** com nomes descritivos
3. **Atualize o bancoModelos** no arquivo `terco.html`
4. **Teste** abrindo a página e verificando se as imagens carregam

## Dicas

- Comece com poucas imagens para testar
- Use nomes de arquivo simples (sem espaços, sem acentos)
- Mantenha backup do código original
- O sistema continua funcionando mesmo sem imagens (usa emojis)

## Status Atual

✅ Logo já configurado  
✅ Uma imagem de pulso já existe  
✅ Sistema de fallback funcionando  
🔄 Precisa adicionar mais imagens  
🔄 Precisa organizar pastas  

---

**Próximo passo:** Escolha uma categoria para começar a adicionar imagens!
