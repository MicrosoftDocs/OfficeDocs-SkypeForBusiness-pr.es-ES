---
title: Configurar la jerarquía de segmentación de equipos
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried, acolonna
search.appverid: MET150
description: Aprenda a configurar una jerarquía de equipos en su organización para publicar contenido en un gran conjunto de equipos.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c5a0fcdce1218bc32eac8b28e7a8c1f41e87cb0
ms.sourcegitcommit: 9787b84ab15ee2e14890151e966c81b4a4d43e62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "49868345"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurar la jerarquía de segmentación de equipos

Configurar una jerarquía de segmentación de equipos permitirá a su organización publicar contenido en un gran conjunto de equipos. La jerarquía de destino del equipo define cómo están relacionados entre sí todos los equipos de la jerarquía, qué usuarios pueden publicar tareas y en qué equipos tienen permisos para publicar. Las características de publicación están deshabilitadas para todos los usuarios a menos que se haya configurado una jerarquía de segmentación de equipos para su organización. Para configurar una jerarquía de segmentación de equipos, deberá crear un archivo que defina la jerarquía y después cargarla en Teams para aplicarla a su organización. Una vez cargado el esquema, las aplicaciones de Teams pueden usarlo.

> [!IMPORTANT]
> Para la versión inicial, solo la aplicación Tareas admite equipos jerárquicos.  Aplicar una jerarquía de destino de grupo a su organización habilitará la [publicación de tareas](https://support.microsoft.com/office/publish-task-lists-to-create-and-track-work-in-your-organization-095409b3-f5af-40aa-9f9e-339b54e705df) en la aplicación Tareas. No verá una jerarquía de equipos en otras áreas de Microsoft Teams.

Este es un ejemplo de cómo se representa la jerarquía en la aplicación Tareas de Teams. Después de crear una lista de tareas, los miembros del equipo de publicación pueden seleccionar los equipos destinatarios a los que enviar (publicar) la lista de tareas. Al seleccionar equipos, el equipo de publicación puede filtrar por jerarquía, por atributos o por una combinación de ambos.<br>

![Captura de pantalla de publicación de tareas](media/manage-tasks-app-publish.png)

## <a name="terminology"></a>Terminología

Los términos siguientes serán importantes al navegar por jerarquías. Teams se denominará **nodos.**

* **Los nodos raíz** son los nodos más altos de la jerarquía. En el ejemplo, Retail Communications es un nodo raíz.
* **Los nodos primarios** **y secundarios son** términos que representan una relación entre dos nodos conectados. En el ejemplo, el Distrito 01 es un nodo secundario del área 1.
* Varios niveles de niños se denominan **"objetos".** El distrito 01, la Tienda 01, la Tienda 03, la Tienda 07, el Distrito 02 y el Distrito 03 son todos miembros del Área 1.
* Un nodo sin hijos se denomina nodo **hoja.** Se encuentran en la parte inferior de una jerarquía.
* **Los equipos destinatarios** son equipos que se han seleccionado para recibir un conjunto específico de contenido que se va a publicar. Deben ser nodos hoja.

## <a name="plan-your-hierarchy"></a>Planear la jerarquía

Antes de crear el esquema que define la jerarquía, debe planear algo y decidir cómo desea dar forma a su organización.  Una de las primeras prioridades es decidir qué grupos organizativos necesitan publicar tareas en otros grupos. Cada nodo de la jerarquía representa un grupo de trabajo o grupo de grupos.

### <a name="permissions-to-publish"></a>Permisos para publicar

El permiso para publicar depende de si un usuario es miembro de cualquier equipo de la jerarquía más la relación de ese equipo o conjunto de equipos con otros equipos de la jerarquía.

> [!NOTE]
> Al propietario de un equipo también se le conceden permisos de publicación.

* Si un usuario es miembro de al menos un equipo que tiene experiencia en la jerarquía, ese usuario puede publicar en esos resultados sin ser miembro de todos los equipos en los que quiera publicar.
* Si un usuario es miembro de un equipo de la jerarquía como mínimo pero no es miembro de ningún equipo con licencia en la jerarquía, ese usuario podrá ver y recibir el contenido publicado de su organización.
* Si un usuario no es miembro de ningún equipo de la jerarquía, dicho usuario no verá ninguna funcionalidad relacionada con la publicación.

### <a name="guidelines"></a>Directrices

* Solo puede haber un archivo de jerarquía aplicado por cada organización. Sin embargo, puede incluir diferentes partes de la organización juntas como jerarquías distintas de nodos dentro de un archivo CSV. Por ejemplo, Contoso Pharmaceuticals tiene un nodo raíz de química y un nodo raíz comercial. Ambos nodos raíz tienen varias filas de solapamientos y no hay superposición entre ellos.
* Solo los nodos hoja pueden ser destinatarios de una publicación. Otros nodos de la jerarquía son útiles para seleccionar los destinatarios de una publicación.
* Un equipo solo puede representarse una vez en una jerarquía.
* Una jerarquía puede contener hasta 15 000 nodos. Planeamos trabajar con los clientes para elevar este límite para organizaciones grandes.

### <a name="example-hierarchy"></a>Jerarquía de ejemplo

Por ejemplo, en la jerarquía siguiente, Recuperación, Comunicaciones y RR. UU. pueden publicar tareas en cada nodo inferior (equipo) de la jerarquía, pero la Zona noreste solo puede publicar tareas en los equipos de la Tienda Nueva York y la Tienda Boston. La jerarquía de ejemplo permite que los grupos Recuperación, Comunicaciones y RR. UU. publiquen tareas que se apliquen a toda la empresa, como la información sobre beneficios o los mensajes del director general. La Zona noreste puede publicar tareas como la programación de personal, información meteorológica, y así sucesivamente, solo en los equipos de la Tienda Nueva York y la Tienda Boston.

![Ejemplo jerárquico de equipos](media/team-targeting-schema-example-new.png)

## <a name="create-your-hierarchy"></a>Crear una jerarquía

> [!NOTE]
> En el resto de este artículo se describe cómo configurar una jerarquía de equipos en el contexto de la publicación de tareas en los equipos destinatarios. Consulte Administrar [la aplicación Tareas de](https://docs.microsoft.com/MicrosoftTeams/manage-tasks-app) su organización en Teams para obtener información general sobre la aplicación Tareas, donde la publicación de tareas aparece cuando está habilitada.

El esquema que define la jerarquía se basa en un archivo de valores separados por comas (CSV). Cada fila del archivo CSV corresponde a un nodo dentro de la jerarquía de equipos. Cada fila contiene información que denomina al nodo dentro de la jerarquía, opcionalmente, lo vincula a un equipo e incluye atributos que se pueden usar para filtrar equipos en aplicaciones que lo admiten.

También puede definir **cubos,** que son categorías que el equipo de publicación puede usar para organizar el contenido enviado a los equipos destinatarios para que les resulte más fácil ver, ordenar y centrarse en el contenido relevante.

### <a name="add-required-columns"></a>Agregar columnas necesarias

El archivo CSV debe contener las tres columnas siguientes, en el orden siguiente, empezando en la primera columna. Para recibir tareas, se debe vincular un nodo a un equipo.

| Nombre de columna   | Obligatorio | Descripción   |
----------------|----------|---------------|
| DisplayName    | Sí      | Este campo es el nombre del nodo. El nombre puede tener hasta 100 caracteres y contener solo los caracteres A-Z, a-z y 0-9. Los nombres de nodo deben ser únicos. |
| ParentName    | Sí       | Este es el nombre del nodo primario. El valor que especifique aquí debe coincidir exactamente con el valor del campo **Nombre Para** Mostrar del nodo primario. Si desea agregar más de un nodo primario, separe cada nombre de nodo primario con un punto y coma (punto ;). Puede agregar hasta 25 nodos primarios y cada nombre de nodo primario puede tener hasta 2.500 caracteres. Un nodo solo puede tener varios nodos primarios si los nodos primarios son nodos raíz.   <br><br>**IMPORTANTE** Tenga cuidado de no crear un bucle en el que un elemento primario en la jerarquía haga referencia a un nodo secundario más bajo de la jerarquía. Esto no es compatible. |
| TeamId        | Sí, si el equipo publica tareas o recibe tareas de un nodo primario       | Esto contiene el id. del equipo al que quiere vincular un nodo. Cada nodo debe hacer referencia a un equipo único, por lo que cada valor de TeamId puede aparecer solo una vez en el archivo de jerarquía. Para obtener el id. de un equipo al que quiere vincular un nodo, ejecute el siguiente comando de `Get-Team | Export-Csv TeamList.csv` PowerShell: Este comando enumera los equipos de su organización e incluye el nombre y el id. de cada equipo. Busque el nombre del equipo con el que desea establecer el vínculo y, a continuación, copie el id. en este campo.|

> [!NOTE]
> Si un nodo no es un nodo raíz o un nodo hoja y no necesita la pertenencia del equipo para conceder los permisos correspondientes de publicación e informes, puede dejar el TeamId en blanco. Este método se puede usar para agregar más granularidad al elegir equipos de destinatarios o para ver informes de finalización sin tener un equipo correspondiente.

### <a name="add-attribute-columns"></a>Agregar columnas de atributo

Después de agregar las tres columnas necesarias, puede agregar columnas de atributo opcionales. Estos atributos se pueden usar para filtrar nodos de forma que pueda seleccionar más fácilmente los que quiere publicar las tareas. Hay dos formas de definir los atributos, dependiendo de si los valores de ese atributo se excluyen mutuamente.

|Formas de agregar atributos|Descripción |Ejemplo  |
|---|---------|---------|
|Si los valores de un atributo se excluyen mutuamente, el nombre de columna que especifique se convierte en el nombre del atributo.|Cada fila puede contener un valor para ese atributo, y cada columna de atributo puede tener un máximo de 50 valores únicos. Cada valor puede tener hasta 100 caracteres. El conjunto de valores de atributo que especifique en la columna de atributo se mostrará como valores de filtro para ese atributo al seleccionar equipos destinatarios con la jerarquía de destino del equipo.|Desea que los usuarios puedan filtrar almacenes por diseño. Los valores de este atributo se excluyen mutuamente porque una tienda solo puede tener un diseño. <br><br>Para agregar un atributo para filtrar almacenes por diseño, agregue una columna denominada Diseño de Tienda. En este ejemplo, los valores del atributo de diseño de Store son Compact, Standard y Large.
|Si necesita indicar varios valores para un atributo y los valores no se excluyen mutuamente, use el formato **AtributoNombre:Valor** Único para los nombres de columna. <br><br>**IMPORTANTE** Asegúrese de usar los dos puntos (dos puntos) solo en inglés (:) como Unicode no es compatible como delimitador de columna de atributo. |La cadena de texto antes de los dos puntos (:) se convierte en el nombre del atributo. Todas las columnas que contienen la misma cadena de texto antes de los dos puntos (:) se agrupan en una sección en el menú de filtrado. Cada una de las cadenas después de los dos puntos se convierten en los valores de esa sección.<br><br>Cada fila puede tener un valor de 0 (cero) o 1 para ese atributo. Un valor 0 significa que el atributo no se aplica al nodo y el valor 1 significa que el atributo se aplica a ese nodo.|Desea que los usuarios puedan filtrar almacenes por departamento. Un almacén puede tener varios departamentos y, por lo tanto, los valores de este atributo no se excluyen mutuamente.<br><br>En este ejemplo, agregamos Departamentos:Ropa, Departamentos:Electronics, Departamentos:Alimentos, Departamentos:Hogar y Jardín, Departamentos:Productos Deportivos como columnas de atributo. Departamentos pasa a ser el nombre del atributo y los usuarios pueden filtrar por los departamentos Ropa, Electrónica, Alimentos, Hogar y Jardín y Productos Deportivos.|

Al agregar una columna de atributo, tenga en cuenta lo siguiente:

* El nombre de columna que especifique o el nombre de columna que especifique antes de los dos puntos (:) se convierte en el nombre del atributo. Este valor se mostrará en las aplicaciones de Teams que usan la jerarquía.
* Puede tener hasta 50 columnas de atributo en la jerarquía.
* El nombre de columna puede tener hasta 100 caracteres y contener solo los caracteres A-Z, a-z y 0-9, y espacios. Los nombres de columna deben ser únicos.

### <a name="add-bucket-columns"></a>Agregar columnas de cubo

Puede agregar columnas de cubo para crear cubos, que son agrupaciones en las que se pueden organizar las tareas. Cada cubo obtiene su propia columna en el archivo CSV. Los cubos que cree estarán disponibles para el equipo de publicación. Después, el equipo de publicación puede usar estos cubos para categorizar las tareas de los equipos destinatarios. Si un cubo aún no existe en un equipo, los cubos se crean a petición cuando se publican las tareas.

Al clasificar los elementos de trabajo una vez de forma centralizada, el equipo de publicación puede organizar previamente la lista de tareas para todos los equipos de decenas, cientos o miles de los destinatarios que reciben la lista de tareas. Los equipos del destinatario pueden ordenar y filtrar sus tareas por cubo para centrarse en el área más relevante para su trabajo.

Cuando agregue una columna de cubo, tenga en cuenta lo siguiente:

* El nombre de columna se convierte en el nombre del cubo. Cada cubo que especifique aparecerá en la lista Cubos en las aplicaciones de Teams que usan la jerarquía.
* Le recomendamos que no incluya información confidencial en los nombres de cubo. En este momento, los equipos de publicación no pueden quitar un cubo mediante la publicación después de crearlo.
* El nombre de columna debe ir precedido por un hashtag (#). Puede tener hasta 100 caracteres y solo contiene los caracteres A-Z, a-z y 0-9. Por ejemplo, #Operations y #Frozen Goods.
* Una jerarquía puede contener hasta 25 columnas de cubo. Tenemos previsto trabajar con los clientes para aumentar este límite para organizaciones más grandes.

### <a name="example"></a>Ejemplo

Este es un ejemplo de un archivo CSV de esquema que se crearía para admitir la jerarquía que se muestra en la imagen anterior. Este esquema contiene lo siguiente:

* Tres columnas necesarias con `TargetName` nombre `ParentName` y `TeamId`
* Tres columnas de atributo `Store layout` `Departments:Clothing` denominadas , y `Departments:Foods`
* Tres columnas de cubo denominadas `Fresh Foods` `Frozen Foods` , y `Women's Wear`

El `Store layout` atributo tiene valores que incluyen , y `Compact` `Standard` `Large` . Las `Departments` columnas de atributo se pueden establecer en un valor de `0` (cero) o `1` . El `Store` diseño y los atributos no se muestran en la imagen `Departments` anterior. Se agregan aquí para ayudar a mostrar cómo se pueden agregar atributos a las entradas de nodo. Lo mismo ocurre con las tres columnas del cubo.

```CSV
"TargetName,ParentName,TeamId,Store layout,Departments:Clothing,Departments:Foods,#Fresh Foods,#Frozen Foods,#Women's Wear"
"Recall,,db23e6ba-04a6-412a-95e8-49e5b01943ba,,,,,,"
"Communications,,145399ce-a761-4843-a110-3077249037fc,,,,,,"
"HR,,,,,,,,,,"
"East Regional Office,,,,,,,,,,"
"West Regional Office,,,,,,,,,,"
"Northeast Zone,East Regional Office,,,,,,,,"
"Southeast Zone,East Regional Office,,,,,,,,"
"New York Store,Northeast Zone,e2ba65f6-25e7-488b-b8f0-b8562d5de60a,Large,1,1,,,"
"Boston Store,Northeast Zone,0454f08a-0507-437c-969a-682eb2fae7fc,Standard,1,1,,,"
"Miami Store,Southeast Zone,619d6e4e-5f68-4b36-8e1f-16c98d7396c1,Compact,0,1,,,"
"New Orleans Store,Southeast Zone,6be960b8-72af-4561-a343-9ac4711874eb,Compact,0,1,,,"
"Seattle Store,West Regional Zone,487c0d20-4e55-4dc2-8187-a24c826e0fee,Standard,1,1,,,"
"Los Angeles Store,West Regional Zone,204a1287-2efb-4a8a-88e0-56fbaf5a2389,Large,1,1,,,"
```

## <a name="apply-your-hierarchy"></a>Aplicar la jerarquía

Una vez que haya definido la jerarquía en el archivo CSV del esquema, estará listo para cargarla en Teams. Para ello, ejecute el comando siguiente. Debe ser administrador global o administrador del servicio de Teams para realizar este paso.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

### <a name="update-your-hierarchy"></a>Actualizar la jerarquía

Puede cargar una nueva jerarquía para reemplazar la antigua con el mismo comando de PowerShell que el anterior. Cada vez que cargue una nueva jerarquía, esta reemplaza a la jerarquía anterior.

### <a name="check-the-status-of-your-hierarchy"></a>Comprobar el estado de la jerarquía

Puede ejecutar el siguiente comando para comprobar el estado de la carga de la jerarquía.

```powershell
Get-TeamTargetingHierarchyStatus
```

El comando devolverá los siguientes campos:

Campo|Descripción
-----|------------
Id. | El identificador único de la carga.
Estado | Estado de carga. Los valores **incluyen Iniciar,** **Validar,** **Correcto** y **Con errores**
ErrorDetails | Detalles si hay un error de carga. Para obtener más información sobre los detalles del error, vea la sección Solución de problemas. Si no hay ningún error, este campo está en blanco.
LastUpdatedAt | Marca de tiempo y fecha de la última vez que se actualizó el archivo.
LastModifiedBy | El id. del último usuario que modificó el archivo.
FileName | El nombre de archivo del CSV.

## <a name="remove-your-hierarchy"></a>Quitar la jerarquía

Si desea deshabilitar inmediatamente la pestaña **Listas** publicadas para todos los usuarios de su organización, puede quitar la jerarquía. Los usuarios no tendrán acceso a la pestaña **Listas publicadas** ni a ninguna de las funcionalidades de la pestaña.  Esto incluye la capacidad de crear nuevas listas de tareas para publicar, obtener acceso a borradores de listas, publicar, anular la publicación y duplicar listas, y ver informes. Al quitar la jerarquía, no se anularán las tareas que se publicaron anteriormente. Estas tareas seguirán estando disponibles para que los equipos de destinatarios las completen.

Para quitar la jerarquía, ejecute el siguiente comando. Debe ser administrador para realizar este paso.

```powershell
Remove-TeamTargetingHierarchy
```

Al confirmar la eliminación, el mensaje de estado seguirá mostrándose que el esquema anterior está presente, aunque intentar eliminar de nuevo devuelve un error que indica que el objeto es nulo.

## <a name="create-a-sample-hierarchy"></a>Crear una jerarquía de ejemplo

### <a name="install-the-teams-powershell-module"></a>Instalar el módulo PowerShell de Teams

> [!IMPORTANT]
> Para realizar este paso, debe instalar y usar el módulo de vista previa pública de PowerShell de Teams desde la galería [de PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams/) Para ver los pasos para instalar el módulo, consulte [Instalar Teams PowerShell.](teams-powershell-install.md)

### <a name="sample-script"></a>Ejemplo de script

El script siguiente se puede usar para crear los equipos y cargar un archivo .csv en su inquilino de Microsoft Teams. Si tiene una jerarquía existente, este script la reemplazará.

#### <a name="create-teams-for-a-simple-hierarchy"></a>Crear equipos para una jerarquía simple

```powershell
$tm1 = New-Team -DisplayName "HQ"
$tm2 = New-Team -DisplayName "North"
$tm3 = New-Team -DisplayName "Store 1"
$tm4 = New-Team -DisplayName "Store 2"
$tm5 = New-Team -DisplayName "South"
$tm6 = New-Team -DisplayName "Store 3"
$tm7 = New-Team -DisplayName "Store 4"
```

#### <a name="use-team-data-to-create-comma-separated-output-displayname-parentname-teamid"></a>Usar los datos del equipo para crear salidas separadas por comas (DisplayName, ParentName, TeamId)

```powershell
$csvOutput = "DisplayName" + "," + "ParentName" + "," + "TeamId" + "`n"
$csvOutput = $csvOutput + $tm1.DisplayName + "," + "," + $tm1.GroupID + "`n"
$csvOutput = $csvOutput + $tm2.DisplayName + "," + $tm1.DisplayName + "," + $tm2.GroupID + "`n"
$csvOutput = $csvOutput + $tm3.DisplayName + "," + $tm2.DisplayName + "," + $tm3.GroupID + "`n"
$csvOutput = $csvOutput + $tm4.DisplayName + "," + $tm2.DisplayName + "," + $tm4.GroupID + "`n"
$csvOutput = $csvOutput + $tm5.DisplayName + "," + $tm1.DisplayName + "," + $tm5.GroupID + "`n"
$csvOutput = $csvOutput + $tm6.DisplayName + "," + $tm5.DisplayName + "," + $tm6.GroupID + "`n"
$csvOutput = $csvOutput + $tm7.DisplayName + "," + $tm5.DisplayName + "," + $tm7.GroupID 
```

#### <a name="save-output-to-a-csv-file-in-the-downloads-folder"></a>Guardar salida en un archivo .csv en la **carpeta Descargas**

```powershell
$csvOutputPath = $env:USERPROFILE + "\downloads\testhierarchy-" + (Get-Date -Format "yyyy-MM-dd-hhmmss") + ".csv" 
$csvOutput | Out-File $csvOutputPath
```

#### <a name="upload-the-hierarchy"></a>Cargar la jerarquía

```powershell
Set-TeamTargetingHierarchy -FilePath $csvOutputPath
Get-TeamTargetingHierarchyStatus
```

## <a name="troubleshooting"></a>Solución de problemas

### <a name="how-to-view-error-details"></a>Cómo ver los detalles del error

Puede ejecutar el comando siguiente para comprender qué está causando un error y devolver los detalles del error.

```powershell
(Get-TeamTargetingHierarchyStatus).ErrorDetails.ErrorMessage
```

### <a name="you-receive-an-error-message-when-you-upload-your-schema-csv-file"></a>Recibe un mensaje de error cuando carga el archivo CSV de esquema

Tenga en cuenta el mensaje de error, ya que debe incluir información de solución de problemas para indicar por qué no se pudo cargar el esquema. Revise y edite el archivo CSV del esquema en función de la información del mensaje de error y vuelva a intentarlo.

### <a name="you-receive-an-error-invalidteamid-error-message-when-you-upload-your-schema-csv-file"></a>Recibe un mensaje de error "Error: InvalidTeamId" al cargar el archivo CSV de esquema

Cuando intenta cargar el archivo CSV de esquema, recibe el siguiente mensaje de error:

```console
Error: InvalidTeamId
Description: TeamID in row # doesn't match a valid Group ID. Please view our documentation to learn how to get the proper GroupID for each team.
```

Compruebe que está usando el TeamId correcto para el equipo en el archivo CSV de esquema. El Id. de equipo debe ser el mismo que el Id. de grupo del grupo de Microsoft 365 que lo copia. Puede buscar el id. de grupo del equipo en el Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro [de administración de Microsoft Teams,](https://admin.teams.microsoft.com/)vaya a **Teams**  >  **Administrar equipos.**
2. Si la **columna Id.** de grupo no  se muestra en la tabla, seleccione Editar columnas en la esquina superior derecha de la tabla y, a continuación, active **Id. de grupo.**
3. Busque el equipo en la lista y, a continuación, busque el Id. de grupo.

Asegúrese de que el Id. de equipo del archivo CSV del esquema coincida con el Id. de grupo que se muestra en el centro de administración de Microsoft Teams.

## <a name="related-topics"></a>Temas relacionados

* [Administrar la aplicación Tareas de su organización en Teams](manage-tasks-app.md)
* [Descripción de PowerShell para Teams](teams-powershell-overview.md)
