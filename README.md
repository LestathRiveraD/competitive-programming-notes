# Competitive Programming: Trigger → Idea

Profiles: [Codeforces (lestat04)](https://codeforces.com/profile/lestat04) · [LeetCode (LestathRiveraD)](https://leetcode.com/u/LestathRiveraD/)


## Number theory and algebra

- Need the GCD of an array split at position `k` → Take the GCD of the two parts: `gcd(a[1..n]) = gcd(gcd(a[1..k]), gcd(a[k+1..n]))`. (Div. 2 1089/C)
- Need the GCD of an array with at least two elements → The GCD of all adjacent-pair GCDs equals the array GCD. (Div. 2 1089/C)
- Need the GCD after removing an element or a contiguous range → Use associativity to combine the GCDs of the remaining prefix and suffix; precompute prefix and suffix GCDs for O(1) queries. (Div. 2 1089/C)
- An argument uses `gcd(a, b) = gcd(lcm(a, b), b)` → Check it before applying it: the identity is false in general (`a = 6, b = 4` gives `2 ≠ 4`). For positive `a` and `b`, the right side is `b`. (Div. 2 1089/C)
- Scheduling events overlap at times that are multiples of several periods → Count overlaps with inclusion–exclusion; use LCMs to describe shared multiples. (Educational 188/C)
- XOR expressions repeatedly contain the same term → Cancel it using `x ^ x = 0`. For `b_i = a_i ^ a_1`, `b_i ^ b_2 = a_i ^ a_2` for `i ≥ 3`; the shared `a_1` disappears. (Div. 4 1090/E)

## Arrays and range queries

- A sliding window's inner loop looks quadratic → Check whether both pointers only move forward; with O(1) work per move, at most `2n` moves give amortized O(n) time. An early break alone does not establish this bound. (Div. 2 1093/B)
- A sliding window needs positions for updates or removals → Store indices instead of values so the element's position remains available. (LeetCode 239, Sliding Window Maximum)
- Static array, associative and idempotent range operation → Build a sparse table in O(n log n); answer a range query in O(1) using two possibly overlapping blocks. (LeetCode 239, Sliding Window Maximum; CSES 1647, Static Range Minimum Queries)
## Graphs and trees

- Adjacent vertices must have opposite values of a binary state → Two-color the graph and check bipartiteness; this also applies to trees. (Div. 4 1090/F)
- Need to identify leaves in a graph or tree → Count each vertex's degree by incrementing both endpoints of every edge; vertices of degree 1 are leaves. (Div. 2 915/B)
