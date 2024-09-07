# Visual Guide to Algorithms

This guide provides advanced visual representations of ten fundamental algorithms using Mermaid charts. These visualizations combine algorithm flowcharts with relevant data structure representations to offer a more intuitive understanding for visual learners.

## 1. Sorting Algorithms (Quicksort)

```mermaid
graph TD
    subgraph Algorithm
        A[Start] --> B["Choose pivot"]
        B --> C["Partition array"]
        C --> D{"Is subarray length > 1?"}
        D -->|Yes| E["Recursively sort left subarray"]
        D -->|Yes| F["Recursively sort right subarray"]
        E --> D
        F --> D
        D -->|No| G[End]
    end
    
    subgraph Array
        H["5 | 2 | 9 | 1 | 7 | 6 | 3"]
        I["3 | 2 | 1 | 5 | 7 | 6 | 9"]
        J["1 | 2 | 3 | 5 | 6 | 7 | 9"]
    end

    H -.-> I
    I -.-> J

    style H fill:#f9f,stroke:#333,stroke-width:2px
    style I fill:#bbf,stroke:#333,stroke-width:2px
    style J fill:#bfb,stroke:#333,stroke-width:2px
```

## 2. Searching Algorithms (Binary Search)

```mermaid
graph TD
    subgraph Algorithm
        A[Start] --> B["left = 0, right = len(arr) - 1"]
        B --> C{"left <= right?"}
        C -->|Yes| D["mid = (left + right) // 2"]
        D --> E{"arr[mid] == target?"}
        E -->|Yes| F["Return mid"]
        E -->|No| G{"arr[mid] < target?"}
        G -->|Yes| H["left = mid + 1"]
        G -->|No| I["right = mid - 1"]
        H --> C
        I --> C
        C -->|No| J["Target not found"]
        F --> K[End]
        J --> K
    end
    
    subgraph Array
        L["1 | 3 | 4 | 6 | 8 | 9 | 11"]
    end

    style L fill:#bfb,stroke:#333,stroke-width:2px
```

## 3. Dynamic Programming (Fibonacci Sequence)

```mermaid
graph TD
    subgraph Algorithm
        A[Start] --> B["Initialize dp array"]
        B --> C["Set base cases: dp[0] = 0, dp[1] = 1"]
        C --> D["For i from 2 to n:"]
        D --> E["dp[i] = dp[i-1] + dp[i-2]"]
        E --> D
        D --> F["Return dp[n]"]
        F --> G[End]
    end
    
    subgraph DP Table
        H["0 | 1 | 1 | 2 | 3 | 5 | 8 | 13"]
    end

    style H fill:#bfb,stroke:#333,stroke-width:2px
```

## 4. Depth-First Search (DFS)

```mermaid
graph TD
    subgraph Algorithm
        A[Start] --> B["Choose start node"]
        B --> C["Mark node as visited"]
        C --> D["For each unvisited neighbor:"]
        D --> E["Recursively apply DFS"]
        E --> D
        D --> F["Backtrack"]
        F --> G[End]
    end
    
    subgraph Graph
        1((1)) --- 2((2))
        1 --- 3((3))
        2 --- 4((4))
        3 --- 4
        3 --- 5((5))
    end

    style 1 fill:#f9f,stroke:#333,stroke-width:4px
    style 2 fill:#bbf,stroke:#333,stroke-width:2px
    style 3 fill:#bbf,stroke:#333,stroke-width:2px
    style 4 fill:#fff,stroke:#333,stroke-width:2px
    style 5 fill:#fff,stroke:#333,stroke-width:2px
```

## 5. Breadth-First Search (BFS)

```mermaid
graph TD
    subgraph Algorithm
        A[Start] --> B["queue = [start]<br/>visited = set([start])"]
        B --> C{"queue empty?"}
        C -->|No| D["node = queue.pop(0)"]
        D --> E["Process node"]
        E --> F["Add unvisited neighbors<br/>to queue and visited"]
        F --> C
        C -->|Yes| G[End]
    end
    
    subgraph Graph
        1((1)) --- 2((2))
        1 --- 3((3))
        2 --- 4((4))
        3 --- 4
        3 --- 5((5))
    end

    style 1 fill:#f9f,stroke:#333,stroke-width:4px
    style 2 fill:#bbf,stroke:#333,stroke-width:2px
    style 3 fill:#bbf,stroke:#333,stroke-width:2px
    style 4 fill:#fff,stroke:#333,stroke-width:2px
    style 5 fill:#fff,stroke:#333,stroke-width:2px
```

## 6. Greedy Algorithms (Coin Change)

```mermaid
graph TD
    subgraph Algorithm
        A[Start] --> B["Sort coins in descending order"]
        B --> C["For each coin:"]
        C --> D["Use as many as possible"]
        D --> E["Subtract from amount"]
        E --> C
        C --> F["Return total coins used"]
        F --> G[End]
    end
    
    subgraph Coins
        H["25¢ | 10¢ | 5¢ | 1¢"]
    end

    style H fill:#bfb,stroke:#333,stroke-width:2px
```

## 7. Divide and Conquer (Merge Sort)

```mermaid
graph TD
    subgraph Algorithm
        A[Start] --> B["If array length > 1:"]
        B -->|Yes| C["Divide array in half"]
        C --> D["Recursively sort left half"]
        C --> E["Recursively sort right half"]
        D --> F["Merge sorted halves"]
        E --> F
        F --> G[End]
        B -->|No| G
    end
    
    subgraph Array
        H["5 | 2 | 9 | 1 | 7 | 6 | 3"]
        I["2 | 5 | 1 | 9 | 3 | 6 | 7"]
        J["1 | 2 | 3 | 5 | 6 | 7 | 9"]
    end

    H -.-> I
    I -.-> J

    style H fill:#f9f,stroke:#333,stroke-width:2px
    style I fill:#bbf,stroke:#333,stroke-width:2px
    style J fill:#bfb,stroke:#333,stroke-width:2px
```

## 8. Recursion (Factorial)

```mermaid
graph TD
    subgraph Algorithm
        A[Start] --> B{"n == 0 or n == 1?"}
        B -->|Yes| C["Return 1"]
        B -->|No| D["Return n * factorial(n-1)"]
        C --> E[End]
        D --> E
    end
    
    subgraph Call Stack
        F["factorial(4)"]
        G["factorial(3)"]
        H["factorial(2)"]
        I["factorial(1)"]
    end

    F -.-> G
    G -.-> H
    H -.-> I

    style F fill:#f9f,stroke:#333,stroke-width:2px
    style G fill:#bbf,stroke:#333,stroke-width:2px
    style H fill:#bfb,stroke:#333,stroke-width:2px
    style I fill:#fbf,stroke:#333,stroke-width:2px
```

## 9. Two-Pointer Technique (String Reversal)

```mermaid
graph TD
    subgraph Algorithm
        A[Start] --> B["left = 0, right = len(s) - 1"]
        B --> C{"left < right?"}
        C -->|Yes| D["Swap s[left] and s[right]"]
        D --> E["left++, right--"]
        E --> C
        C -->|No| F["Return reversed string"]
        F --> G[End]
    end
    
    subgraph String
        H["H | E | L | L | O"]
        I["O | E | L | L | H"]
    end

    H -.-> I

    style H fill:#f9f,stroke:#333,stroke-width:2px
    style I fill:#bfb,stroke:#333,stroke-width:2px
```

## 10. Sliding Window (Max Sum Subarray)

```mermaid
graph TD
    subgraph Algorithm
        A[Start] --> B["Initialize window sum"]
        B --> C["For each window:"]
        C --> D["Add next element"]
        D --> E["Subtract first element"]
        E --> F["Update max sum if needed"]
        F --> C
        C --> G["Return max sum"]
        G --> H[End]
    end
    
    subgraph Array
        I["1 | 4 | 2 | 10 | 23 | 3 | 1 | 0 | 20"]
        J["Window 1"]
        K["Window 2"]
        L["Window 3"]
    end

    I -.-> J
    I -.-> K
    I -.-> L

    style I fill:#bfb,stroke:#333,stroke-width:2px
    style J fill:#f9f,stroke:#333,stroke-width:2px
    style K fill:#bbf,stroke:#333,stroke-width:2px
    style L fill:#fbf,stroke:#333,stroke-width:2px
```
