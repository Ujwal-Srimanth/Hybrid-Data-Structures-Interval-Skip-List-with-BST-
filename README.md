## Hybrid-Data-Structures-Interval-Skip-List-with-BST-

# Overview
This code implements an Interval Skip List (ISL) combined with a Binary Search Tree (BST). The combination leverages the BST to speed up the range-based operations by quickly navigating to the relevant range within the skip list structure. Each node in the BST represents a different range segment, allowing for efficient traversal and search within specific ranges. This approach is particularly useful for performing operations over intervals or ranges.

# Key Components
Classes
Node: Represents a single node within a skip list, holding min and max values for an interval, as well as pointers to the next and down nodes.

SkipList: The primary class for the skip list data structure, where intervals (ranges) are stored. Operations include:

insert: Adds a new range to the skip list.
delete: Removes a range from the skip list.
search: Searches for a given range within the skip list.
display: Prints the skip list, showing each level for visualization.
BST: A binary search tree where each node represents a different interval and points to a skip list. The BST enables faster navigation to relevant skip lists, allowing for rapid access to desired ranges based on the minimum value in each interval. Key methods include:

add_child: Inserts a new node into the BST.
display_helper: Collects and returns all skip lists in the BST for visualization.
search_helper: Initiates a search in the skip lists corresponding to the range.
Helper Functions
bui: Builds a BST based on predefined range intervals.
search_helper: Searches for a range in the appropriate skip list by traversing the BST.
display_helper2: Displays all levels of the skip lists stored in the BST.
insert_helper: Determines the correct skip list for insertion based on the range interval.
delete_helper: Finds and deletes a range from the appropriate skip list by navigating through the BST.
# Usage Instructions
# Initial Setup
The code initializes multiple skip lists for specific range intervals (e.g., 1-1000, 1000-10000, etc.).
Each interval in the BST points to a specific skip list, allowing for efficient insertion, deletion, and search operations within defined ranges.
Menu Options
After setup, you can interact with the program via a menu with the following options:

Insert: Adds a new range to the appropriate skip list.
Delete: Removes a specified range from the appropriate skip list.
Display: Displays all skip lists with each level for visualization.
Search: Searches for a specific range within the skip lists, using the BST to speed up the lookup.
Exit: Terminates the program.
Example Workflow
Insert: Enter the lower and upper bounds of the range. The code determines which skip list to insert into based on the interval.
Delete: Specify the lower and upper bounds of the range you wish to delete. The code will locate the range within the relevant skip list and delete it if found.
Search: Specify the bounds for a range to check if it exists in any skip list. The BST directs the search to the relevant skip list, improving search efficiency.
Display: Outputs each level in each skip list for all intervals, aiding in visualization and debugging.
Performance Optimization
Using a BST as a layer over the skip list improves performance by allowing the program to skip entire sections of the range based on BST nodes. For instance, if searching for a range that falls within 75000-100000, the BST quickly navigates to this range, avoiding other ranges like 1-75000.

Example Usage
To run the program:

Compile and execute the code.
Follow the menu prompts to insert, delete, display, or search for ranges.
The program is particularly useful for applications requiring dynamic interval management with efficient range-based operations.
