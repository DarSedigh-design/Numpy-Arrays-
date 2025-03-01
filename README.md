import numpy as np
import pandas as pd


def display_array_info(arr, name="Array"):
    """Displays an array with its shape, size, data type, and contents."""
    print(f"\n{name} Details:")
    print(f"Shape: {arr.shape}, Size: {arr.size}, Data Type: {arr.dtype}")
    print(arr)


def create_and_display_arrays():
    """Creates various NumPy arrays and displays them."""

    # 1D Array
    arr_1d = np.array([1, 2, 3, 4, 5])
    display_array_info(arr_1d, "1D Array")

    # 2D Array
    arr_2d = np.array([[10, 20, 30], [40, 50, 60], [70, 80, 90]])
    display_array_info(arr_2d, "2D Array")

    # 3D Array
    arr_3d = np.array([[[1, 2], [3, 4]], [[5, 6], [7, 8]]])
    display_array_info(arr_3d, "3D Array")


def create_random_array(rows, cols):
    """Generates a random NumPy array with given dimensions."""
    return np.random.randint(1, 100, size=(rows, cols))


def display_as_dataframe(arr):
    """Displays a NumPy array as a Pandas DataFrame for better visualization."""
    df = pd.DataFrame(arr)
    print("\nArray as DataFrame:")
    print(df)


def array_statistics(arr):
    """Displays basic statistical details of an array."""
    print("\nArray Statistics:")
    print(f"Mean: {np.mean(arr):.2f}, Median: {np.median(arr):.2f}")
    print(f"Min: {np.min(arr)}, Max: {np.max(arr)}, Std Dev: {np.std(arr):.2f}")


def main():
    print("NumPy Array Demonstration\n")

    # Display predefined arrays
    create_and_display_arrays()

    # User-defined random array
    rows = int(input("\nEnter number of rows for a random array: "))
    cols = int(input("Enter number of columns: "))

    random_arr = create_random_array(rows, cols)
    display_array_info(random_arr, "Random Array")
    display_as_dataframe(random_arr)
    array_statistics(random_arr)


if __name__ == "__main__":
    main()
