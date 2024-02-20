# Priorities
You are given an array of `n` integers and a number K. The integers in the array represent customer IDs, and the number of times an ID appears in the array indicates how frequently that customer has visited. Your task is to find the top K unique IDs corresponding to the most frequent customers.  prioritize the customer with the higher ID number.

from collections import Counter

def top_k_customers(n, customer_ids, k):
    id_counts = Counter(customer_ids)

    sorted_ids = sorted(id_counts.keys(), key=lambda x: (-id_counts[x], -x))

    for i in range(min(k, len(sorted_ids))):
        print(sorted_ids[i], end=" ")

n = int(input())
customer_ids = list(map(int, input().split()))
k = int(input())

top_k_customers(n, customer_ids, k)
