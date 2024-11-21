# Multi-Dimentiional-Arrays-C-


1. 2D Arrays

Initialization

int packages [] [4] {

    {1,2,3,4},
    
    {5,6,7,8},
    
    {9,10,11,12},
    
    {3,4,5,6}
    
};

    A 2D array (packages) is created with 4 rows and 4 columns.
    
    Since the number of rows isn't specified, the compiler determines it automatically.

Reading 2D Arrays

Using Loops

for(size_t i{0} ; i < 3; ++ i){

    for(size_t j{0}; j < 4 ; ++j){
    
        cout << packages[i][j] << "   ";
        
    }
    
    cout << endl;
    
}

    Loops iterate over the rows (i) and columns (j) to print each element.
    
    size_t is used for indexing, which ensures non-negative integers.

Using size

for(size_t i{0} ; i < size(packages); ++ i){

    for(size_t j{0}; j < size(packages[i])  ; ++j){
    
        cout << packages[i][j] << "   ";
        
    }
    
    cout << endl;
}

    size (C++17) determines the array dimensions dynamically.
    
    This makes the loop independent of hardcoding sizes.
    

2. 3D Arrays
   
Initialization

int house_block [7][5][3] {
    {
        {1,2,3}, {4,5,6}, {7,8,9}, {10,11,12}, {13,14,15}
        
    },
    
    ...
};

    house_block is a 3D array representing 7 houses, each with 5 rooms, and each room has 3 lights.
    
    Each {} group corresponds to the inner-most dimensions.

Reading 3D Arrays

for(size_t i{0}; i < size(house_block); ++i){

    for(size_t j{0}; j < size(house_block[i]); ++j){
    
        for(size_t k{0}; k < size(house_block[i][j]); ++k){
        
            cout << house_block[i][j][k] << "     ";
            
        }
        cout << endl;
    }
}

    Three nested loops iterate over each dimension:
    
        i for houses, j for rooms, k for lights.

Omitting Dimensions

For 2D Arrays

int packages2 [] [5] {

    {1,2,3},
    
    {4,5,6},
    
    ...
    
};

    Only the left-most dimension is omitted, letting the compiler calculate it automatically.
    
    In the output loop, std::size determines sizes for both dimensions dynamically.

For 3D Arrays

int house_block1 [] [5] [3] {
    {
        {1,2,3}, {4,5,6}, ...
        
    },
    
    ...
};

    The left-most dimension is omitted. The compiler infers it from the initialization.

Automatic Zero-Filling

If fewer elements are initialized than the specified size, C++ fills the remaining spots with 0.
Example

int house_block2 [] [5] [4] {
    {
    
        {1,2,3}, {4}, ...
        
    },
    
    ...
};

    Second dimension: {4} will be filled with 0 to form {4, 0, 0, 0}.
    
    Third dimension: Empty spots are also filled with 0.

Data Modification

house_block2[0][2][1] = 1021;

    This modifies a specific element in the 3D array.

Key Concepts

    Multi-dimensional arrays: Nested structures for organizing data.
    
    Dynamic querying: Use size for better scalability.
    
    Zero-filling: The compiler auto-fills missing elements with 0.
    
    Data manipulation: Arrays can be updated at specific indices.

