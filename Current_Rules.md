**RULES:**
1. **Main Clause Extraction**
   - **Trigger:** ROOT token of the sentence, which is usually a verb
   - **Action:** Extract the ROOT and its immediate subtree.  
   - **Subjects:** nsubj or `nsubjpass` ** if missing, add previous subject to the beginning, which is an imperfect rule
   - **Objects/Complements:** `dobj`, `attr`, `xcomp` 
   - **Example Output:** `<Subj> <ROOT lemma> <Obj(s)>`

2. **Relative Clauses**
   - **Trigger:** Tokens with `dep_ = relcl` under ROOT  
   - **Action:** Extract subtree,  if subject missing, add previous subject to the beginning
   - **Example Output:** `<Subj> <VERB> <Obj(s)>`

3. **Complement (adv) Clauses**
   - **Trigger:** `advcl`, `ccomp`, or `xcomp` under ROOT  
   - **Action:** Extract full subtree; if subject missing, add previous subject to the beginning

4. **Appositions (nom) Facts**
   - **Trigger:** `attr` or `appos` tokens, which are typically nouns
   - **Action:** Convert to `<Subj> is <Appos>`, which is an **imperfect rule**

5. **Prepositional Clauses**
   - **Trigger:** `prep` + `pobj`  
   - **Action:** Extract preposition and object, and,  if subject missing, add previous subject to the beginning

6. **Coordinating Conjunctions**
   - **Trigger:** `conj` under ROOT  
   - **Action:** Form atomic sentence: `<Subj> <Conj verb>`  

7. **Remove Duplicates**
   - Remove duplicate atomic sentences. need to find a way to maintain the correct order
