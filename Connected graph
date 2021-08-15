def connected_graph(graph):
    '''
    The definition for connected graph is that all the vertices will be connected to all the other vertices exclude themselves.
    Our stipulation here will be either isolated vertex or connected to less than the number of keys - the vertex himself.
    '''
    for neighbor in graph:
        if graph[neighbor] == [] or len(graph[neighbor]) < len(graph.keys()) - 1:
            return False
        
    return True
