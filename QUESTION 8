class ListNode:
    def __init__(self, val=0, next=None):
        self.val = val
        self.next = next

def delete_zero_sum_sublists(head):
    dummy = ListNode(0)
    dummy.next = head

    current = dummy
    running_sum = 0
    sum_dict = {}

    while current:
        running_sum += current.val

        if running_sum in sum_dict:
            # Remove nodes between the two occurrences of the sum
            start = sum_dict[running_sum].next
            temp_sum = running_sum + start.val
            while temp_sum != running_sum:
                del sum_dict[temp_sum]
                start = start.next
                temp_sum += start.val
            sum_dict[running_sum].next = current.next
        else:
            sum_dict[running_sum] = current

        current = current.next

    return dummy.next
