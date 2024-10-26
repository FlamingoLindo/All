
# Instalação python

```python
pip install selenium
```


# Localizadores

## O que são localizadores?

Localizadores são utilizados para identificar algum elemento em uma página.

---

## Quais são os tipos de localizadores?

| Tipo | Descrição |
|------|-----------|
|class name|Localiza elementos cujo nome de classe contém o valor de pesquisa (nomes de classes compostos não são permitidos)|
|css selector|Localiza elementos que correspondem a um seletor CSS|
|id|Localiza elementos cujo atributo ID corresponde ao valor de pesquisa|
|name|Localiza elementos cujo atributo NAME corresponde ao valor pesquisado|
|link text|Localiza elementos âncora cujo texto visível corresponde ao valor de pesquisa|
|partial link text|Localiza elementos âncora cujo texto visível contém o valor de pesquisa. Se vários elementos corresponderem, apenas o primeiro será selecionado|
|tag name|Localiza elementos cujo nome da tag corresponde ao valor de pesquisa|
|xpath|Localiza elementos que correspondem a uma expressão XPath|

Essa tabela foi retirada do site do [Selenium](https://www.selenium.dev/documentation/webdriver/elements/locators/)

---

## Qual tipo de seletor usar?

**1. CSS Selector:**

- É geralmente mais rápido e confiável quando possível, especialmente em navegadores modernos.

- Ideal para selecionar elementos com base em classes, IDs ou atributos específicos.

- Útil para identificar elementos de forma precisa e concisa, especialmente quando a estrutura da página é estável.


**2. XPath:**

- Permite maior flexibilidade, pois pode navegar por estruturas complexas e hierarquias.

- Recomendado quando há necessidade de localizar elementos relativos, como "o segundo elemento após um título específico".

- É útil quando os elementos não têm identificadores únicos.


**3. Full XPath:**

- Utiliza o caminho completo até o elemento na árvore do DOM, indo desde o nó raiz.

- É mais suscetível a mudanças na estrutura da página, pois qualquer alteração no layout pode quebrar o seletor.

- Use-o apenas em última instância, caso os outros métodos não consigam localizar o elemento, e o layout seja estável.


# Imports

## webdriver

```python
from selenium import webdriver
```

## By

```python
from selenium.webdriver.common.by import By
```

## Wait e Expected conditions
```python
from selenium.webdriver.support.ui import WebDriverWait
from selenium.webdriver.support import expected_conditions as EC
```
# Código

## Drivers

```python
driver_chrome = webdriver.Chrome() 
driver_firefox = webdriver.Firefox() 
driver_edge = webdriver.Edge()
```

## Fechar o driver
```python
driver.quit()
```

## Abrir um site
```python
driver.get('twitch.tv/flamingo_lindo')
```

## Encontrar um elemento (simples)

```python
like_btn = driver.find_element(By.CSS_SELECTOR, '.ktLpvM')
```

## Definir tempo de espera do driver

```python
wait = WebDriverWait(driver, 5)
```
## Encontrar um elemento (esperar ele aparecer)

```python
like_btn = wait.until(EC.presence_of_element_located((By.CSS_SELECTOR, '.ktLpvM')))
```
