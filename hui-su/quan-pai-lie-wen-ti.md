# 全排列问题

问题：输入一个整数数组，**数组中可能包含重复元素**，返回所有不重复的排列。

{% code fullWidth="true" %}
```cpp
/* 回溯算法：全排列 */
void backtrack(vector<int> &state, vector<int> &choices, vector<bool> &selected, vector<vector<int>> &res) {
    // 当状态长度等于元素数量时，记录解
    if (state.size() == choices.size()) {
        res.push_back(state);
        return;
    }
    // 遍历所有选择
    unordered_set<int> duplicated;
    for (int i = 0; i < choices.size(); i++) {
        int choice = choices[i];
        // 剪枝：不允许重复选择元素 且 不允许重复选择相等元素
        //selected剪子孙节点，duplicated剪兄弟节点
        if (!selected[i] && duplicated.find(choice) == duplicated.end()) {
            // 尝试：做出选择，更新状态
            duplicated.emplace(choice); // 记录选择过的元素值
            selected[i] = true;
            state.push_back(choice);
            // 进行下一轮选择
            backtrack(state, choices, selected, res);
            // 回退：撤销选择，恢复到之前的状态
            selected[i] = false;
            state.pop_back();
        }
    }
}

/* 全排列 */
vector<vector<int>> permutations(vector<int> nums) {
    vector<int> state;
    vector<bool> selected(nums.size(), false);
    vector<vector<int>> res;
    backtrack(state, nums, selected, res);
    return res;
}
```
{% endcode %}
