import math
import random

def unvisited_vertices(graph):
    '''
    Creating a set of all the unvisited vertices.
    '''
    unvisitedSet = set()

    for vertex in graph:
        unvisitedSet.add(vertex)
        
    return unvisitedSet
-------------------------------------------
def vertex_distance(graph, initialVertex):
    '''
    Assigning distance value to every node: zero for the initial vertex and infinity for all other vertices.
    '''
    vertexDistance = {}
    
    for vertex in graph:
        if vertex == initialVertex:
            vertexDistance[vertex] = 0
        
        else:
            vertexDistance[vertex] = math.inf
            
    return vertexDistance
-------------------------------------------    
def edge_distance(graph, initialVertex):
    '''
    Assigning distance value to every edge.
    '''
    edgeDistance = {}
    
    for vertex in graph:
        for neighbor in graph[vertex]:
            if neighbor + vertex in edgeDistance.keys():
                pass
            
            elif neighbor == initialVertex:
                edgeDistance[neighbor + vertex] = random.randint(1, 30)
            
            else:
                edgeDistance[vertex + neighbor] = random.randint(1, 30)
        
    return edgeDistance
-------------------------------------------
#Introducing the graph to the user.
graph = edges_in_dictionary(links)
print(f"Your current graph is:\n{graph}\n")

#Creating a set of all the unvisited vertices.
unvisitedSet = unvisited_vertices(graph)
print(f"Unvisited vertices:\n{unvisitedSet}\n")

#Taking user input for the initial vertex, and performs a check whether the chosen vertex is isolated.
userInput = input(f"Please enter the vertex you want to be the initial (a-f): ")

while graph[userInput] == []:
    print("Your chosen vertex is isolated, please choose other vertex.")
    userInput = input("Please enter the vertex you want to be the initial (a-f): ")

print("\n")
#Assigning distance value to every node: zero for the initial vertex and infinity for all other vertices.
vertexDistance = vertex_distance(graph, userInput)
print(f"Vertices labels:\n{vertexDistance}\n")

#Sets the initial vertex as current.
currentVertex = userInput

#Assigning distance value to every edge.
edgeDistance = edge_distance(graph, userInput)
print(f"The distances:\n{edgeDistance}\n")

#Logic.
for vertex in graph:
    if vertex == currentVertex:
        tempVertex = ""
        
        while currentVertex in unvisitedSet:
             for neighbor in graph[currentVertex]:
                    if vertexDistance[neighbor] == math.inf and neighbor in unvisitedSet:
                        if currentVertex + neighbor in edgeDistance.keys():
                            vertexDistance[neighbor] = vertexDistance[currentVertex] + edgeDistance[currentVertex + neighbor]
                        
                        else:
                            vertexDistance[neighbor] = vertexDistance[currentVertex] + edgeDistance[neighbor + currentVertex]
                    
                    elif neighbor not in unvisitedSet:
                            pass
                    
                    else:
                        if currentVertex + neighbor in edgeDistance.keys():
                            if vertexDistance[neighbor] > vertexDistance[currentVertex] + edgeDistance[currentVertex + neighbor]:
                                vertexDistance[neighbor] = vertexDistance[currentVertex] + edgeDistance[currentVertex + neighbor]
                            
                        else:
                            if vertexDistance[neighbor] > vertexDistance[currentVertex] + edgeDistance[neighbor + currentVertex]:
                                vertexDistance[neighbor] = vertexDistance[currentVertex] + edgeDistance[neighbor + currentVertex]
             
            minimum = math.inf   
             for neighbor in graph[currentVertex]:
                if neighbor in unvisitedSet:
                    if vertexDistance[neighbor] < minimum:
                        minimum = vertexDistance[neighbor]
                        tempVertex = neighbor
                
             unvisitedSet.remove(currentVertex)
             currentVertex = tempVertex
                
print(f"The result:\n{vertexDistance}")
