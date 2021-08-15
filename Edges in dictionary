def edges_in_dictionary(links):
    '''
    From list of lists or tuples to dictionary.
    '''
    graph = {}
    
    for vertex in links:
        if vertex[0] not in graph.keys():
            graph[vertex[0]] = []
         
        if vertex[1] != None:
            graph[vertex[0]].append(vertex[1])
        
    return graph

'''
None is indicating that the vertex is isolated.
'''
links = [['a', 'c'], ['b', 'c'], ['b', 'e'], ['c', 'a'], ['c', 'b'], ['c', 'd'], ['c', 'e'], ['d', 'c'], ['e', 'c'], ['e', 'b'], ['f', None]]
