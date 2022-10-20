+ [Search two sum](#search-two-sum)
+ [Search second min](#search-second-min)

## Search two sum

Данные отсортированы в неубывающем порядке. Найти два таких индекса i и j, что numb[i] + numb[j] == k
```python
def search_two_sum(numb, k):
    numb_copy = numb.copy()
    numb_copy.sort() #не обязательно
    left = 0
    right = len(numb_copy)-1
    while left < right:
        if numb_copy[left] + numb_copy[right] == k:
            return [left, right]
        elif numb_copy[left] + numb_copy[right] < k:
            left = left + 1
        else:
            right = right - 1
            
    return [-1, -1]
```


## Search second min


```python
def search_second_min(lst):
    mini = 999
    second_mini = 999
    for i, elem in enumerate(lst):
        if elem < mini:
            mini = elem
    lst.remove(mini)
    for i, elem in enumerate(lst):
        if elem < second_mini:
            second_mini = elem
    return second_mini
    
print(search_second_min([-5, -3, 1, 3, 10, 15, 20]))```
