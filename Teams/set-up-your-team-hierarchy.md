---
title: Configurar la jerarquía de segmentación de equipos
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: Aprenda a configurar una jerarquía de equipos en su organización para publicar contenido en un gran conjunto de equipos.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 099ee82e5890e81b6fc89a5ffc1842d936e6ad1e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806160"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurar la jerarquía de segmentación de equipos

> **Esta característica está actualmente en versión preliminar privada.**

Para crear una jerarquía de equipos que pueda usar su organización para publicar contenido en un gran conjunto de equipos, debe configurar el esquema de segmentación de equipos. El esquema define cómo se relacionan entre sí todos los equipos de la jerarquía y los atributos que se pueden usar para filtrar sus equipos. Después de crear el esquema, súbalo a Teams y la jerarquía se aplicará en toda la organización. Una vez cargado el esquema, las aplicaciones del cliente de Teams pueden usarlo. 

> [!IMPORTANT]
> No verá una jerarquía de equipos cuando esté explorando equipos o canales dentro de ellos. Para ver la jerarquía de los equipos, debe usar una aplicación que la admita. Para la versión inicial, solo la aplicación Tareas admite equipos jerárquicos. En el resto de este artículo se describe cómo configurar una jerarquía de equipos en el contexto de la publicación de tareas en los equipos destinatarios. Antes de configurar la jerarquía de segmentación de equipos, vea Administrar la aplicación Tareas de su organización en [Teams](manage-tasks-app.md) para obtener información general sobre la publicación de tareas.

Este es un ejemplo de cómo se representa la jerarquía en la aplicación Tareas de Teams. Después de crear una lista de tareas, los miembros del equipo de publicación pueden seleccionar los equipos destinatarios a los que enviar (publicar) la lista de tareas. Al seleccionar equipos, el equipo de publicación puede filtrar por jerarquía, por atributos o por una combinación de ambos.<br>

![Captura de pantalla de publicación de tareas](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>Planear la jerarquía

Antes de crear el esquema que define la jerarquía, debe hacer cierta planificación y decidir cómo desea dar forma a su organización. Esto incluye decidir qué grupos de la organización necesitan publicar tareas en otros grupos. Cada nodo de la jerarquía representa un grupo de trabajo o grupo de grupos. Los nodos en la parte inferior de la jerarquía (los que no tienen hijos) son equipos que pueden recibir tareas, mientras que otros nodos (padres) son grupos de la organización con permiso para publicar tareas hacia abajo. Un equipo solo puede representarse una vez en la jerarquía.

Por ejemplo, en la siguiente jerarquía, Recuperación, Comunicaciones comerciales y RR. UU., puede publicar tareas en cada nodo inferior (equipo) de la jerarquía, mientras que la Zona Norte solo puede publicar tareas en los equipos de la Tienda Nueva York y el Almacén de Boston. Esta jerarquía permite que los grupos Recuperación, Comunicaciones comerciales y RR. UU. publiquen tareas que se apliquen a toda la empresa, como la información sobre beneficios o los mensajes del director general. La Zona Norte puede publicar tareas, como la programación de personal, información meteorológica, entre otras, solo en los equipos de la Tienda Nueva York y la Tienda Boston.

![Ejemplo jerárquico de equipos](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>Crear una jerarquía

El esquema que define la jerarquía se basa en un archivo de valores separados por comas (CSV). Cada fila del archivo CSV corresponde a un nodo dentro de la jerarquía de equipos. Cada fila contiene información que nombra el nodo dentro de la jerarquía, opcionalmente, lo vincula a un equipo e incluye atributos que se pueden usar para filtrar equipos en aplicaciones que lo admiten.

También puede definir cubos, que son categorías que el equipo de publicación puede usar para organizar el contenido enviado a los equipos destinatarios para que les resulte más fácil ver, ordenar y centrarse en el contenido relevante.

### <a name="add-required-columns"></a>Agregar columnas necesarias

El archivo CSV debe contener las tres columnas siguientes, en el orden siguiente, empezando en la primera columna. Para que un nodo reciba tareas, debe estar vinculado a un equipo. Durante la vista previa privada, se admiten 2.000 nodos. Al iniciarse, esperamos admitir al menos 15 000 nodos de forma predeterminada. Planeamos trabajar con los clientes para elevar este límite para organizaciones grandes.

| Nombre de columna   | Obligatorio | Descripción   |
----------------|----------|---------------|
| TargetName    | Sí      | Este es el nombre del nodo. El nombre puede tener hasta 100 caracteres y contener solo los caracteres A-Z, a-z y 0-9. Los nombres de nodo deben ser únicos. |
| ParentName    | Sí       | Este es el nombre del nodo primario. El valor que especifique aquí debe coincidir exactamente con el valor del campo NombreDe TargetName del nodo primario. Si desea agregar más de un nodo primario, separe cada nombre de nodo primario con un punto y coma (punto ;). Puede agregar hasta 25 nodos primarios y cada nombre de nodo primario puede tener hasta 2500 caracteres. Un nodo solo puede tener varios nodos primarios si los nodos primarios son nodos raíz.   <br><br>**IMPORTANTE** Tenga cuidado de no crear un bucle en el que un elemento primario en la jerarquía haga referencia a un nodo secundario más bajo de la jerarquía. Esto no es compatible. |
| TeamId        | Sí, si el equipo publica tareas o recibe tareas de un nodo primario       | Esto contiene el id. del equipo al que quiere vincular un nodo. Un nodo debe estar vinculado a un equipo si se encuentra en la parte inferior de la jerarquía, si quiere que los usuarios puedan publicar desde ese nodo o si desea que los usuarios puedan ver los informes de ese nodo y sus propiedades. Por ejemplo, si el administrador de La Región Oeste de Office desea ver el informe de finalización de tareas de los nodos que pertenecen a esa región.<br><br>Si desea agregar un nodo solo con el fin de agrupar otros nodos de la jerarquía, no es necesario vincular ese nodo a un equipo y puede dejar este campo en blanco. Puede vincular cada nodo a un solo equipo.<br>Para obtener el identificador de un equipo al que quiere vincular un nodo, ejecute el siguiente comando de `Get-Team | Export-Csv TeamList.csv` PowerShell: Esto muestra los equipos de su organización e incluye el nombre y el identificador de cada equipo. Busque el nombre del equipo con el que desea establecer el vínculo y, a continuación, copie el id. en este campo.|

### <a name="add-attribute-columns"></a>Agregar columnas de atributo

Después de agregar las tres columnas necesarias, puede agregar columnas de atributo opcionales. Estos atributos se pueden usar para filtrar nodos de modo que pueda seleccionar más fácilmente los que quiere publicar las tareas. Hay dos formas de definir los atributos, dependiendo de si los valores de ese atributo se excluyen mutuamente.

|Formas de agregar atributos|Descripción |Ejemplo  |
|---|---------|---------|
|Si los valores de un atributo se excluyen mutuamente, el nombre de columna que especifique se convierte en el nombre del atributo.|Cada fila puede contener un valor para ese atributo y cada valor puede tener hasta 100 caracteres. El conjunto de valores de atributo que especifique en la columna de atributo se mostrará como valores de filtro disponibles para ese atributo en las aplicaciones de Teams que usan la jerarquía. Cada columna de atributo puede tener hasta 50 valores únicos. |Desea que los usuarios puedan filtrar almacenes por diseño. Los valores de este atributo se excluyen mutuamente porque una tienda solo puede tener un diseño. <br><br>Para agregar un atributo para filtrar almacenes por diseño, agregue una columna denominada Diseño de Tienda. En este ejemplo, los valores del atributo de diseño de Store son Compact, Standard y Large.
|Si necesita indicar varios valores para un atributo y los valores no se excluyen mutuamente, use el formato **AtributoNombre:Valor** Exclusivo para los nombres de columna. |La cadena de texto antes de los dos puntos (:) se convierte en el nombre del atributo. Todas las columnas que contienen la misma cadena de texto antes de los dos puntos (:) se agrupan en una sección en el menú de filtrado. Cada una de las cadenas después de los dos puntos se convierten en los valores de esa sección.<br><br>Cada fila puede tener un valor de 0 (cero) o 1 para ese atributo. Un valor 0 significa que el atributo no se aplica al nodo y el valor 1 significa que el atributo se aplica a ese nodo.|Desea que los usuarios puedan filtrar almacenes por departamento. Un almacén puede tener varios departamentos y, por lo tanto, los valores de este atributo no se excluyen mutuamente.<br><br>En este ejemplo, agregamos Departamentos:Ropa, Departamentos:Electronics, Departamentos:Alimentos, Departamentos:Hogar y Jardín, Departamentos:Productos deportivos como columnas de atributo. Departamentos pasa a ser el nombre del atributo y los usuarios pueden filtrar por los departamentos Ropa, Electrónica, Alimentos, Hogar y Jardín y Productos Deportivos.|

Al agregar una columna de atributo, tenga en cuenta lo siguiente:

- El nombre de columna que especifique o el nombre de columna que especifique antes de los dos puntos (:) se convierte en el nombre del atributo. Este valor se mostrará en las aplicaciones de Teams que usan la jerarquía.
- El nombre de columna puede tener hasta 100 caracteres y contener solo los caracteres A-Z, a-z y 0-9, y espacios. Los nombres de columna deben ser únicos.
- En el inicio, planeamos permitir 50 columnas de atributo.

### <a name="add-bucket-columns"></a>Agregar columnas de cubo

Puede agregar columnas de cubo para crear cubos, que son agrupaciones en las que se pueden organizar las tareas. Cada cubo obtiene su propia columna en el archivo CSV. Los cubos que cree estarán disponibles para el equipo de publicación. Después, el equipo de publicación puede usar estos cubos para categorizar las tareas de los equipos destinatarios. Si un cubo aún no existe en un equipo, los cubos se crean a petición cuando se publican las tareas.

Al clasificar el trabajo una vez de forma centralizada, el equipo de publicación puede organizar previamente la lista de tareas para todos los equipos de decenas, centenas o miles de los destinatarios que reciben la lista de tareas. Los equipos del destinatario pueden ordenar y filtrar las tareas por cubo para centrarse en el área más relevante para su trabajo.

Cuando agregue una columna de cubo, tenga en cuenta lo siguiente:

- El nombre de columna se convierte en el nombre del cubo. Cada cubo que especifique aparecerá en la lista Cubos en las aplicaciones de Teams que usan la jerarquía. Le recomendamos que no incluya información confidencial en los nombres de cubo. En este momento, los equipos de publicación no pueden quitar un cubo mediante la publicación después de crearlo.
- El nombre de columna debe ir precedido por un hashtag (#). Puede tener hasta 100 caracteres y solo contiene los caracteres A-Z, a-z y 0-9. Por ejemplo, #Operations y #Frozen Goods.
- En el lanzamiento, esperamos admitir 25 columnas de cubo. Tenemos previsto trabajar con los clientes para aumentar este límite para organizaciones más grandes.

### <a name="example"></a>Ejemplo

He aquí un ejemplo de un archivo CSV de esquema que se crearía para admitir la jerarquía que se muestra en la imagen anterior. Este esquema contiene lo siguiente:

- Tres columnas necesarias con `TargetName` nombre `ParentName` y `TeamId`
- Tres columnas de atributo denominadas `Store layout` `Departments:Clothing` , y `Departments:Foods`
- Tres columnas de cubo denominadas `Fresh Foods` `Frozen Foods` , y `Womenswear`

El `Store layout` atributo tiene valores que incluyen , y `Compact` `Standard` `Large` . Las `Departments` columnas de atributo se pueden establecer en un valor de `0` (cero) o `1` . El `Store` diseño y los atributos no se muestran en la imagen `Departments` anterior. Se agregan aquí para ayudar a mostrar cómo se pueden agregar atributos a las entradas de nodo. Lo mismo ocurre con las tres columnas del cubo.


| TargetName             | ParentName                      | TeamId                       | Diseño de la Tienda|Departamentos:Ropa|Departamentos:Alimentos|#Fresh Alimentos|#Frozen Alimentos|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| Recuperar                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| Comunicaciones         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| RR. HH.                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| Oficina regional de East   |                         |                                      |||||||
| Oficina regional del oeste   |                         |                                      |||||||
| Zona Noreste        | Oficina regional de East    |                                      |||||||
| Zona Sur-Este        | Oficina regional de East    |                                      |||||||
| Tienda de Nueva York         | Zona Noreste         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |Grande|1|1||||
| Almacén de Boston           | Zona Noreste         | 0454f08a-0507-437c-969a-682eb2fae7fc |Standard|1|1||||
| Miami Store            | Zona Sur-Este         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |Compactar|0|1||||
| Nueva Store de Orleans      | Zona Sur-Este         | 6be960b8-72af-4561-a343-9ac4711874eb |Compactar|0|1||||
| Seattle Store          | Oficina regional del oeste    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |Standard|1|1||||
| Store de Los Ángeles      | Oficina regional del oeste    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |Grande|1|1||||

## <a name="apply-your-hierarchy"></a>Aplicar la jerarquía

> [!IMPORTANT]
> Para realizar este paso, debe instalar y usar el módulo de vista previa pública de PowerShell de Teams desde la galería [de PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/) Para ver los pasos para instalar el módulo, vea [Instalar Teams PowerShell.](teams-powershell-install.md)

Una vez que haya definido la jerarquía en el archivo CSV del esquema, estará listo para cargarla en Teams. Para ello, ejecute el comando siguiente. Debe ser administrador global o administrador del servicio de Teams para realizar este paso.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>Quitar la jerarquía

> [!IMPORTANT]
> Para realizar este paso, debe instalar y usar el módulo de vista previa pública de PowerShell de Teams desde la galería [de PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/) Para ver los pasos para instalar el módulo, vea [Instalar Teams PowerShell.](teams-powershell-install.md)

Si desea deshabilitar inmediatamente la pestaña **Listas** publicadas para todos los usuarios de su organización, puede quitar la jerarquía. Los usuarios no tendrán acceso a la pestaña **Listas publicadas** ni a ninguna de las funciones de la pestaña.  Esto incluye la capacidad de crear nuevas listas de tareas para publicar, obtener acceso a borradores de listas, publicar, anular la publicación y duplicar listas, y ver informes. Al quitar la jerarquía, no se publican las tareas que se publicaron anteriormente. Estas tareas seguirán estando disponibles para que los equipos de destinatarios las completen. 

Para quitar la jerarquía, ejecute el siguiente comando. Debe ser administrador para realizar este paso. 

```powershell
Remove-TeamTargetingHierarchy
```

## <a name="troubleshooting"></a>Solución de problemas

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Recibe un mensaje de error cuando carga el archivo CSV de esquema

Tenga en cuenta el mensaje de error, ya que debe incluir información de solución de problemas para indicar por qué no se pudo cargar el esquema. Revise y edite el archivo CSV del esquema en función de la información del mensaje de error y vuelva a intentarlo.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Recibe un mensaje de error "Error: InvalidTeamId" al cargar el archivo CSV de esquema

Cuando intenta cargar el archivo CSV de esquema, recibe el siguiente mensaje de error:

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Compruebe que está usando el TeamId correcto para el equipo en el archivo CSV de esquema. El Id. de equipo debe ser el mismo que el Id. de grupo del grupo de Microsoft 365 que copia el equipo. Puede buscar el id. de grupo del equipo en el Centro de administración de Microsoft Teams. 

1. En el panel de navegación izquierdo del Centro de administración de [Microsoft Teams,](https://admin.teams.microsoft.com/)vaya a **Teams**  >  **Administrar equipos.**
2. Si la **columna Id.** de grupo no  se muestra en la tabla, seleccione Editar columnas en la esquina superior derecha de la tabla y, a continuación, active **Id. de grupo.**
3. Busque el equipo en la lista y, a continuación, busque el Id. de grupo.

Asegúrese de que el Id. de equipo del archivo CSV del esquema coincida con el Id. de grupo que se muestra en el centro de administración de Microsoft Teams. 

## <a name="related-topics"></a>Temas relacionados

- [Administrar la aplicación Tareas de su organización en Teams](manage-tasks-app.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
