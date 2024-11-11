#Source code:

from difflib import get_close_matches


class Node:
    def __init__(self, name, details):
        self.name = name
        self.details = details


class AutoMapperPipeline:
    def __init__(self, output_nodes):
        # Store output nodes as a dictionary for easier lookup
        self.output_data = {node.name: node.details for node in output_nodes}

    def get_closest_match(self, input_name, threshold=0.6):
        """
        Finds the closest match for an input node name in the output nodes.
        If a match meets the threshold, returns the matched output node name and its details.
        """
        closest_matches = get_close_matches(input_name, self.output_data.keys(), n=1, cutoff=threshold)

        if closest_matches:
            closest_match = closest_matches[0]
            return closest_match, self.output_data[closest_match]
        else:
            return None, "No similar variable found. Please check your input."

    def map_single_node(self, input_name, threshold=0.6):
        """
        Maps a single input node to the closest matching output node.
        Returns the matched name and details.
        """
        match, details = self.get_closest_match(input_name, threshold)
        if match:
            print(f"Did you mean '{match}'? Details: {details}")
        else:
            print("No suitable match found. Please try again.")


# Example usage
if __name__ == "__main__":
    # Define output nodes with names and details
    output_nodes = [
        Node("FirstName", "Prashant"),
        Node("MiddleName", "Kumar"),
        Node("LastName","Mishra"),
        Node("E mail", "pk200130@gmail.com"),
        Node("phone no.", "9479391901"),
        Node("D.O.B","30-09-2002."),
        Node("Age", "22"),
        Node("Intern at", "Fusion eze"),
        Node("studying at","VIT Bhopal"),
    ]

    # Initialize the pipeline with output nodes
    pipeline = AutoMapperPipeline(output_nodes)

    # Loop to take multiple user inputs
    while True:
        input_name = input("Enter a variable name to get details (or type 'exit' to quit): ")
        if input_name.lower() == 'exit':
            break
        pipeline.map_single_node(input_name, threshold=0.6)
