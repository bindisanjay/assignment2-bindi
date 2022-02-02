# Sanjay Bindi

###### Cafe Niloufer Hyderabad

This place is famous for Tea and is situated in **Hyderabad, Telangana**. Chai or Tea in Hyderabad, represents an emotion. It is widely consumed throughout the day! A special place in the hearts of all Hyderabadis, Chai is beautifully embodied in Hyderabad's culture and lifestyle. Also, there are many restaurants in Nampally which serves different cuisines.

---

 In depth details

---

The closest airport to the location is Rajiv Gandhi International Airport, Shamshabad which is 18 miles from Cafe Niloufer.

Step by step directions for travelling from RGIA to Cafe Niloufer :

1. Follow Airport Approach Road to NH 44 in Madhura Nagar.
2. Continue on NH 44. Take PV Narasimha Rao Expy to Inner Ring Rd/Masab Tank Road/Mehdipatnam - Banjara Hills Rd/Utkoor - Mogdumpur Rd in Ex Service Men Colony.
3. Continue on Inner Ring Rd/Masab Tank Road/Utkoor - Mogdumpur Rd to your destination in Red Hills.

An unordered list of specific foods items at Cafe Niloufer that i recommend are

* Snacks

  * Tea
  * Coffee

  [Linking About Me](https://github.com/bindisanjay/assignment2-bindi/blob/main/AboutMe.md)

---

Sports

---

We can see the games available within the community in below table

|   Sport   |   Address   |  Price  |
| :-------: | :---------: | :-----: |
| Badminton |   Sharjah   | 76.54 $ |
|  Archery  | Arch Center | 23.76 $ |
|   Rugby   | Ball Center |  53 $  |
|  Tennis  |   T-Park   |  88 $  |

---

    Pithy Quotation

---

> “Nobody reaches anywhere by believing.”

― *Osho*

> “One doesn't expect a falcon to pull a plow, or a butterfly to cook your breakfast.”

― *Katherine Blake, The Interior Life*

---
Code Fencing
---

> Dynamic programming is both a mathematical optimization method and a computer programming method. The method was developed by Richard Bellman in the 1950s and has found applications in numerous fields, from aerospace engineering to economics.

[Click this for more on Dynamic Programming](https://en.wikipedia.org/wiki/Dynamic_programming)

Finding the largest Zero Sub Matrix
~~~

int zero_matrix(vector<vector<int>> a) {
    int n = a.size();
    int m = a[0].size();

    int ans = 0;
    vector<int> d(m, -1), d1(m), d2(m);
    stack<int> st;
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < m; ++j) {
            if (a[i][j] == 1)
                d[j] = i;
        }

        for (int j = 0; j < m; ++j) {
            while (!st.empty() && d[st.top()] <= d[j])
                st.pop();
            d1[j] = st.empty() ? -1 : st.top();
            st.push(j);
        }
        while (!st.empty())
            st.pop();

        for (int j = m - 1; j >= 0; --j) {
            while (!st.empty() && d[st.top()] <= d[j])
                st.pop();
            d2[j] = st.empty() ? m : st.top();
            st.push(j);
        }
        while (!st.empty())
            st.pop();

        for (int j = 0; j < m; ++j)
            ans = max(ans, (i - d[j]) * (d2[j] - d1[j] - 1));
    }
    return ans;
}
~~~

[Click on this for Code](https://cp-algorithms.com/dynamic_programming/zero_matrix.html)







