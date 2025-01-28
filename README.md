def find_subarray_with_sum(arr, target):
    start = 0
    current_sum = 0
    for end in range(len(arr)):
        current_sum += arr[end]
        while current_sum > target and start <= end:
            current_sum -= arr[start]
            start += 1

        
        if current_sum == target:
            return arr[start:end + 1]

    
    return None


arr = list(map(int, input("Enter the elements of the array (space separated): ").split()))
target = int(input("Enter the target sum: "))


result = find_subarray_with_sum(arr, target)

if result:
    print("Subarray found:", result)
else:
    print("No subarray found with the given target sum.")
