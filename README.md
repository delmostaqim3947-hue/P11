import numpy as np

# 1. Création de la matrice (3 élèves, 4 matières)
# Chaque ligne représente un élève
notes = np.array([
    [12, 15, 10, 17],
    [8,  9,  11, 10],
    [14, 16, 15, 19]
])

# 2. Calcul de la moyenne par ligne (par élève)
# axis=1 signifie qu'on calcule la moyenne horizontalement
# keepdims=True est crucial pour garder la shape (3, 1) et permettre le broadcasting
moyennes_eleves = np.mean(notes, axis=1, keepdims=True)

# 3. Soustraction vectorisée (Broadcasting)
# notes est (3, 4) - moyennes_eleves est (3, 1)
# NumPy "étire" les moyennes sur 4 colonnes automatiquement
notes_centrees = notes - moyennes_eleves

print("Moyennes par élève :\n", moyennes_eleves)
print("\nNotes centrées (écart à la moyenne) :\n", notes_centrees)
