# Initialize an empty dictionary to store the data
seasons_dict = {}

try:
    # Open the input file and read its contents
    with open(input_file, 'r') as file:
        lines = file.readlines()

    i = 0
    while i < len(lines):
        # Read the number of seasons and TV show
        num_seasons = int(lines[i].strip())
        tv_show = lines[i + 1].strip()

        # Check if num_seasons is already a key in the dictionary
        if num_seasons in seasons_dict:
            # Append the TV show to the existing list
            seasons_dict[num_seasons].append(tv_show)
        else:
            # Create a new key-value pair in the dictionary
            seasons_dict[num_seasons] = [tv_show]

        # Move to the next set of lines
        i += 2

    # Sort the dictionary by keys (ascending order)
    sorted_by_keys = dict(sorted(seasons_dict.items()))

    # Write the sorted results to output_keys.txt
    with open("output_keys.txt", 'w') as keys_file:
        for key, value in sorted_by_keys.items():
            keys_file.write(f"{key}: {'; '.join(value)}\n")

    # Flatten the dictionary values into a single list for sorting by titles
    all_shows = [show for shows in sorted_by_keys.values() for show in shows]

    # Sort the list of TV shows alphabetically
    sorted_shows = sorted(all_shows)

    # Write the sorted results to output_titles.txt
    with open("output_titles.txt", 'w') as titles_file:
        for show in sorted_shows:
            titles_file.write(f"{show}\n")

    print("Results have been written to output_keys.txt and output_titles.txt.")

except FileNotFoundError:
    print(f"File '{input_file}' not found.")
except Exception as e:
    print(f"An error occurred: {str(e)}")
