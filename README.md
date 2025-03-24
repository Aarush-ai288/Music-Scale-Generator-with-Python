# Music-Scale-Generator-with-Python
This code takes a desired key and major or minor as input and returns the appropriate scale.
def scaleGen(note, major_minor):
    alpha = ["A", "A#", "B", "C", "C#", "D", "D#", "E", "F", "F#", "G", "G#"]
    majorPattern = [0, 2, 4, 5, 7, 9, 11, 12]
    minorPattern = [0, 2, 3 ,5, 7, 8, 10, 12]
    ret_lst = []
    n = note.upper()
    m = major_minor.lower()
    note_idx = alpha.index(n)
    chromatic_lst = list(alpha[note_idx: ] + alpha[:note_idx + 1])
    if m == "major":
        for vals in majorPattern:
            ret_lst.append(chromatic_lst[vals])
    else:
        for vals in minorPattern:
            ret_lst.append(chromatic_lst[vals])
    ret_str = " ".join(ret_lst)
    return n + " " + m + ":\n" + ret_str +"\n"

print(scaleGen("G#", "minor"))
print(scaleGen("C", "majOR"))
print(scaleGen("d", "MAJoR"))
