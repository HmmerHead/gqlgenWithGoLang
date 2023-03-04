# gqlgenWithGoLang
## GraphQL com Go

Para estudo, utilizei o [Type-safe GraphQL for Go](https://gqlgen.com/) que, segundo a documentação: 

> is a Go library for building GraphQL servers without any fuss.

Subistituindo as informações que vieram por padrão, criei um servidor simples para realizar uma listagem de algum valores e tendo o mysql como banco para armazenar tudo. Também é possilve usar o sqlite para testes, tendo apenas como opção remover o comentario. 

Rodar o projeto

> go run cmd/server/server.go

Consultas


```
mutation createCategory {
  createCategory(input:
    {name: "Cat-2", description: "desc-cat-2"}) 
  {
  	id
  	name
  	description
  }
}

mutation createCourse {
  createCourse(input:
    {name: "Course-2", description: "desc-course-2", categoryId: "db4dddc4-d468-4adc-8895-b0f9de3a97f3"}) 
  {
  	id
  	name
  	description
  }
}

query queryCategoryWithCourses {
  categories {
    id
    name
    description
    courses {
      name
    }
  }
}


query queryCoursesWithCategory {
  courses {
    id
    name
    description
    category {
      name
    }
  }
}
```

Criação

![image](https://user-images.githubusercontent.com/26328503/222906487-873ada86-f21c-4330-9753-0e098a1fac93.png)

![image](https://user-images.githubusercontent.com/26328503/222906516-902af072-4ccd-4292-961d-594e5a923546.png)

Listagem

![image](https://user-images.githubusercontent.com/26328503/222906534-f3a271d4-606a-4516-be5f-6fcfdfb056c4.png)

![image](https://user-images.githubusercontent.com/26328503/222906549-28338986-5048-490c-a2e2-76d12f137d25.png)

