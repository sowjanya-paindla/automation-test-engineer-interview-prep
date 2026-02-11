##Find duplicate elements in a list##
s = [1, 2, 3, 2, 4, 5, 1]

printed = []

for i in s:
    if s.count(i) > 1 and i not in printed:
        print(i)
        printed.append(i)

