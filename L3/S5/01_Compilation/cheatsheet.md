<div dir="rtl" align="right">

# 📝 ورقة الغش - Compilation

> مراجعة سريعة قبل الامتحان

---

## 🔄 مراحل الترجمة (Phases de Compilation)

```
Code Source → [Analyse Lexicale] → Tokens
           → [Analyse Syntaxique] → Arbre Syntaxique
           → [Analyse Sémantique] → Arbre Annoté
           → [Génération Code Intermédiaire] → Code 3 Adresses
           → [Optimisation] → Code Optimisé
           → [Génération Code] → Code Machine
```

---

## 📌 قبل الفرض - نقاط أساسية

### التحليل المعجمي (Analyse Lexicale)

- [ ] التعابير النظامية (Expressions Régulières)
  - `a*` : صفر أو أكثر من a
  - `a+` : واحد أو أكثر من a
  - `a?` : صفر أو واحد من a
  - `a|b` : a أو b
  - `[a-z]` : أي حرف من a إلى z

- [ ] الـ Automates
  - AFN → AFD (تحويل)
  - Minimisation de l'AFD

- [ ] أنواع الـ Tokens
  - Mots-clés: `if`, `while`, `for`
  - Identificateurs: `variable`, `fonction`
  - Opérateurs: `+`, `-`, `*`, `/`
  - Séparateurs: `;`, `,`, `(`, `)`

### التحليل النحوي (Analyse Syntaxique)

- [ ] أنواع القواعد
  - Grammaire LL(1): تحليل من اليسار
  - Grammaire LR: تحليل من اليمين

- [ ] حساب First و Follow
  ```
  First(α): أول رمز طرفي يمكن أن يبدأ به α
  Follow(A): الرموز التي يمكن أن تأتي بعد A
  ```

- [ ] جدول التحليل LL(1)
  - الصفوف: Non-terminaux
  - الأعمدة: Terminaux
  - الخلايا: قواعد الإنتاج

### التحليل الدلالي (Analyse Sémantique)

- [ ] جدول الرموز (Table des Symboles)
- [ ] التحقق من الأنواع (Vérification de Types)
- [ ] النطاق (Portée des Variables)

### توليد الكود (Génération de Code)

- [ ] كود ثلاثي العناوين (Code 3 Adresses)
  ```
  t1 = a + b
  t2 = t1 * c
  x = t2
  ```

- [ ] أشكال التعليمات
  - `x = y op z`
  - `x = op y`
  - `x = y`
  - `goto L`
  - `if x goto L`

---

## 📐 صيغ مهمة

### تحويل AFN إلى AFD

```
ε-closure(s): جميع الحالات الممكن الوصول إليها من s عبر ε
move(T, a): الحالات الممكن الوصول إليها من T عبر الرمز a
```

### First و Follow

```
First(ε) = {ε}
First(a) = {a}  // a terminal
First(Aα) = First(A) - {ε} ∪ (if ε ∈ First(A) then First(α))

Follow(S) ⊇ {$}  // S = start symbol
A → αBβ: Follow(B) ⊇ First(β) - {ε}
A → αB: Follow(B) ⊇ Follow(A)
```

---

## ⚠️ أخطاء شائعة

| الخطأ | التصحيح |
|:------|:--------|
| نسيان ε في First | تحقق دائماً إذا كان Non-terminal يمكن أن ينتج ε |
| خلط بين AFN و AFD | AFD: حالة واحدة لكل انتقال، AFN: عدة حالات |
| نسيان $ في Follow(S) | دائماً Follow(Start) يحتوي $ |

---

## 🔗 روابط سريعة

- [📘 فهرس المقياس](README.md)
- [📖 قاموس المصطلحات](glossary.md)
- [⬆️ فهرس السداسي](../00_Index.md)

</div>
