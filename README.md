# Find-Maximum-Sum
A number n can be broken into three parts n/2,  n/3,  and n/4 (take the integer part only). Each number obtained in this process can be divided further recursively.  Find the maximum sum that can be obtained by summing up the divided parts together. We stop dividing when we cannpot further divide.

def find_maximum_sum(n):
    dp = [0] * (n + 1)

    for i in range(1, n + 1):
        dp[i] = max(i, dp[i // 2] + dp[i // 3] + dp[i // 4])

    return dp[n]

n = int(input())
print(find_maximum_sum(n))
