* users
  - id (primary key , serial)
  - username (varchar(100) NOT NULL)
  - email (varchar(100) NOT NULL)
  - password (varchar(200) NOT NULL)

* projects
  - id (primary key , serial)
  - title(varchar(100) NOT NULL)
  - description(text DEFAULT no description)
  - feature boolean DEFAULT false
  - client varchar(100)
  - location varchar(100)
  - date(date)

* categories
  - id (primary key , serial)
  - title(varchar(100) NOT NULL)
  - parent (id from the same table)

* project-category
  - id (primary key , serial)
  - project_id (FK(projects(id)))
  - category_id (FK(categories(id)))

* materials
  - id (primary key , serial)
  - title(varchar(100) NOT NULL)
  - description(text DEFAULT no description)

* attributes
  - id (primary key , serial)
  - title(varchar(100) NOT NULL)
  - type(varchar(100) NOT NULL)

* material-attribute
  - id (primary key , serial)
  - value varchar(100) NOT NULL
  - material_id (FK(materials(id)))
  - attribute_id (FK(attributes(id)))

* material-pictures
  - id (primary key , serial)
  - material_id (FK(materials(id)))
  - main boolean DEFAULT false

* project-pictures
  - id (primary key , serial)
  - project_id (FK(projects(id)))
  - main boolean DEFAULT false

* project-material
  - id (primary key , serial)
  - material_id (FK(materials(id)))

* calculator
  - id (primary key , serial)
  - description(text DEFAULT 'no description')
  - type varchar(100) NOT NULL
  - price DOUBLE NOT NULL
