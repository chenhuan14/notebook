# Delta Lake 

## 简介

Lakehouse是一种将数据湖（Data Lake）和数据仓库（Data Warehouse）的优点结合起来的数据架构模式。传统的数据湖主要关注数据存储和数据处理的灵活性，但在数据管理方面存在挑战，如缺乏事务性、数据一致性和可靠性。而数据仓库则提供了强大的数据管理功能，但对于半结构化和非结构化数据的支持有限。

Delta Lake通过在数据湖之上引入事务性、一致性和可靠性的特性，填补了数据湖和数据仓库之间的空白。它在数据湖中提供了ACID事务支持、数据版本控制、元数据管理等功能，让数据湖更加可靠、可管理和可查询。同时，Delta Lake保持了数据湖的灵活性，可以处理各种类型的数据，包括结构化、半结构化和非结构化数据。

因此，Delta Lake可以看作是一种Lakehouse技术，将数据湖和数据仓库的优点结合起来，提供了一个更全面的数据管理解决方案。

## 二进制文件存储	

Delta Lake主要是为结构化数据设计的，而不是为存储大型二进制文件（如图片）而设计的。虽然Delta Lake可以存储二进制文件，但不建议将其用于存储超大型的单个文件。

对于存储大型二进制文件，建议使用专门的对象存储服务，如Amazon S3、Azure Blob Storage或Google Cloud Storage等。这些服务为存储大型二进制文件提供了高可用性、可扩展性和持久性。

如果您希望将图片与结构化数据相关联，并且使用Delta Lake进行管理，则可以考虑在Delta Lake中存储图片相关的元数据，如文件路径、图片名称、大小、创建时间等信息，而不是直接存储图片本身。实际的图片文件可以存储在对象存储服务中，并通过链接或标识符与Delta Lake中的元数据进行关联。

这种方式可以让您在Delta Lake中进行结构化数据和图片元数据的查询和管理，同时确保图片文件的高效存储和处理。
