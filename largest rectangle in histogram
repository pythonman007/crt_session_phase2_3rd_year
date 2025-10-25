class Solution:
    def largestRectangleArea(self, heights: List[int]) -> int:
        def find_nse(heights):
            n = len(heights) 
            stack = [] 
            ans = [0]*n 
            for i in range(n-1,-1,-1):
                while(len(stack)!=0 and heights[stack[-1]]>=heights[i]):
                    stack.pop()
                if(len(stack) == 0):
                    ans[i] = len(heights) 
                else:
                    ans[i] = stack[-1] 
                stack.append(i)
            return ans 
        def find_pse(heights):
            n = len(heights) 
            stack = [] 
            ans = [0]*n 
            for i in range(0,n): 
                while(len(stack)!=0 and heights[stack[-1]]>=heights[i]):
                    stack.pop()
                if(len(stack) == 0):
                    ans[i] = -1 
                else:
                    ans[i] = stack[-1] 
                stack.append(i)
            return ans 
        nse = find_nse(heights) 
        pse = find_pse(heights) 
        area = 0 
        maxArea = 0 
        for i in range(0,len(heights)):
            area = heights[i]*(nse[i]-pse[i]-1) 
            maxArea = max(area,maxArea) 
        return maxArea
