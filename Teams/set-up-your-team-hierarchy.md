---
title: Configurar la jerarquía de destino de su equipo
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
description: Aprenda a configurar una jerarquía de equipo en su organización para publicar contenido en un gran conjunto de equipos.
audience: admin
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2bb8133733f7230715753ecea0118fc635af446b
ms.sourcegitcommit: 6e24ea8aa9cccf8a1a964c8ed414ef5c7de3dc17
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159007"
---
# <a name="set-up-your-team-targeting-hierarchy"></a>Configurar la jerarquía de destino de su equipo

> **Esta característica está actualmente en versión preliminar privada.**

Para crear una jerarquía de equipos que su organización puede usar para publicar contenido en un gran conjunto de equipos, debe configurar el esquema de destino del equipo. El esquema define cómo se relacionan entre sí todos los equipos de la jerarquía y los atributos que se pueden usar para filtrar los equipos. Después de crear el esquema, lo carga en Teams y la jerarquía se aplica en toda la organización. Una vez cargado el esquema, las aplicaciones del cliente de Teams pueden usarlo. 

> [!IMPORTANT]
> No verá una jerarquía de equipos cuando está explorando equipos o canales dentro de ellos. Para ver la jerarquía de Teams, debe usar una aplicación que la admita. En la versión inicial, solo la aplicación tareas admite equipos jerárquicos. En el resto de este artículo se describe la configuración de una jerarquía de equipo en el contexto de las tareas de publicación para los equipos de destino. Antes de configurar la jerarquía de destino de su equipo, vea [administrar la aplicación tareas de su organización en Teams](manage-tasks-app.md) para obtener información general sobre la publicación de tareas.

Este es un ejemplo de cómo se representa la jerarquía en la aplicación tareas de Teams. Después de crear una lista de tareas, los miembros del equipo de publicación pueden seleccionar a los equipos de destino para enviar (publicar) la lista de tareas. Al seleccionar Teams, el equipo de publicación puede filtrar por jerarquía, por atributos o una combinación de ambos.<br>

![Captura de pantalla de la publicación de tareas](media/manage-tasks-app-publish.png)

## <a name="plan-your-hierarchy"></a>Planear la jerarquía

Antes de crear el esquema que define su jerarquía, debe realizar alguna planificación y decidir cómo desea dar forma a su organización. Esto incluye decidir qué grupos organizativos necesitan publicar tareas en otros grupos. Cada nodo de la jerarquía representa un grupo de trabajo o un grupo de grupos. Los nodos de la parte inferior de la jerarquía (que no tienen elementos secundarios) son equipos que pueden recibir tareas mientras otros nodos (primarios) son grupos organizativos con permisos para publicar tareas hacia abajo. Un equipo solo se puede representar una hora de la jerarquía.

Por ejemplo, en la siguiente jerarquía, RECALL, las comunicaciones minoristas y HR, pueden publicar tareas en cada nodo inferior (equipo) de la jerarquía, mientras que la zona de noreste solo puede publicar tareas en la tienda de Nueva York y en los equipos de la tienda Boston. Esta jerarquía permite a los grupos de recuperación, comunicaciones minoristas y de RRHH publicar tareas que se aplican a toda la empresa, como información sobre beneficios o mensajes del Director Ejecutivo. La zona de noreste puede publicar tareas, como la programación de personal, información meteorológica, etc., solo en la tienda de Nueva York y en los equipos de la tienda Boston.

![Ejemplo jerárquico de equipo](media/team-targeting-schema-example.png)

## <a name="create-your-hierarchy"></a>Crear la jerarquía

El esquema que define la jerarquía se basa en un archivo de valores separados por comas (CSV). Cada fila del archivo CSV corresponde a un nodo dentro de la jerarquía de Teams. Cada fila contiene información que nombra el nodo dentro de la jerarquía, opcionalmente, lo vincula a un equipo e incluye atributos que se pueden usar para filtrar los equipos en las aplicaciones que lo admiten.

También puede definir cubos, que son las categorías que el equipo de publicación puede usar para organizar el contenido enviado a los equipos de los destinatarios para que le resulte más fácil ver, ordenar y centrarse en el contenido relevante.

### <a name="add-required-columns"></a>Agregar columnas obligatorias

El archivo CSV debe contener las tres columnas siguientes, en el orden siguiente, empezando por la primera columna. Un nodo debe estar vinculado a un equipo para que pueda recibir tareas. En Private Preview, admitimos nodos 500. En el inicio, esperamos admitir al menos 2.000 nodos de forma predeterminada. Tenemos pensado trabajar con clientes para aumentar este límite para organizaciones de mayor tamaño.

| Nombre de columna   | Obligatorio | Descripción   |
----------------|----------|---------------|
| NombreDeDestino    | Sí      | Este es el nombre del nodo. El nombre puede tener hasta 100 caracteres y contener solo los caracteres A-Z, a-z y 0-9. Los nombres de nodo deben ser únicos. |
| ParentName    | Sí       | Este es el nombre del nodo primario. El valor que especifique aquí debe coincidir exactamente con el valor del campo TargetName del nodo primario. Si desea agregar más de un nodo primario, separe cada nombre de nodo primario con un punto y coma (;). Puede Agregar hasta 25 nodos primarios y cada nombre de nodo primario puede tener hasta 2500 caracteres. Un nodo solo puede tener varios nodos primarios si los nodos primarios son nodos raíz.   <br><br>**Importante** Tenga cuidado de no crear un bucle en el que un elemento primario situado más arriba en la jerarquía haga referencia a un nodo secundario situado en la parte inferior de la jerarquía. Esto no es compatible. |
| TeamID        | Sí, si el equipo publica tareas o recibe tareas desde un nodo principal       | Contiene el identificador del equipo al que desea vincular un nodo. Un nodo debe estar vinculado a un equipo si está en la parte inferior de la jerarquía, si quiere que los usuarios puedan publicar desde ese nodo, o si desea que los usuarios puedan ver los informes de ese nodo y sus descendientes. Por ejemplo, si su jefe de la región oeste, Office quiere ver informes de finalización de tareas para los nodos que pertenecen a esa región.<br><br>Si desea agregar un nodo solo para el propósito de agrupar otros nodos en la jerarquía, no es necesario vincular ese nodo a un equipo y dejar este campo en blanco. Puede vincular cada nodo a un solo equipo.<br>Para obtener el identificador de un equipo al que desea vincular un nodo, ejecute el siguiente comando de PowerShell `Get-Team | Export-Csv TeamList.csv`:. En esta lista se enumeran los equipos de su organización y se incluyen el nombre y el identificador de cada equipo. Busque el nombre del equipo con el que desea establecer el vínculo y, a continuación, copie el identificador en este campo.|

### <a name="add-attribute-columns"></a>Agregar columnas de atributos

Después de agregar las tres columnas obligatorias, puede Agregar columnas de atributos opcionales. Estos atributos se pueden usar para filtrar los nodos de modo que sea más fácil seleccionar aquellos a los que desea publicar las tareas. Hay dos maneras de definir los atributos, en función de si los valores de ese atributo se excluyen mutuamente.

|Formas de agregar atributos|Descripción |Ejemplo  |
|---|---------|---------|
|Si los valores de un atributo son mutuamente excluyentes, el nombre de columna que especifique se convertirá en el nombre del atributo.|Cada fila puede contener un valor para ese atributo, y cada valor puede tener hasta 100 caracteres. El conjunto de valores de atributo que especifique en la columna atributo se mostrará como valores de filtro disponibles para ese atributo en las aplicaciones de teams que usan la jerarquía. Cada columna de atributos puede tener hasta 50 valores únicos. |Quiere que los usuarios puedan filtrar tiendas por diseño. Los valores de este atributo son mutuamente excluyentes porque un almacén solo puede tener un diseño. <br><br>Para agregar un atributo a los almacenes de filtro por diseño, agregue una columna denominada diseño de tienda. En este ejemplo, los valores para el atributo de diseño de tienda son compacto, estándar y grande.
|Si necesita indicar varios valores para un atributo y los valores no se excluyen mutuamente, use el formato **attributeName: UniqueValue** para los nombres de columna. |La cadena de texto antes de los dos puntos (:) se convierte en el nombre del atributo. Todas las columnas que contienen la misma cadena de texto antes de los dos puntos (:) se agrupan en una sección en el menú de filtrado. Cada una de las cadenas después de los dos puntos se convierten en los valores de esa sección.<br><br>Cada fila puede tener el valor 0 (cero) o 1 para ese atributo. Un valor de 0 significa que el atributo no se aplica al nodo y un valor de 1 significa que el atributo se aplica a ese nodo.|Quiere que los usuarios puedan filtrar tiendas por departamento. Una tienda puede tener varios departamentos y, por lo tanto, los valores para este atributo no se excluyen mutuamente.<br><br>En este ejemplo, agregamos departamentos: ropa, departamentos: electrónica, departamentos: alimentos, departamentos: hogar y jardín, departamentos: artículos deportivos como columnas de atributos. Departamentos se convierte en el nombre del atributo y los usuarios pueden filtrar por los departamentos de ropa, electrónica, comidas, casa y jardín, así como de material deportivo.|

Cuando agregue una columna de atributos, tenga en cuenta lo siguiente:

- El nombre de columna que especifique o el nombre de columna que especifique antes del signo de dos puntos (:) se convierte en el nombre del atributo. Este valor se mostrará en las aplicaciones de teams que usan la jerarquía.
- El nombre de columna puede tener hasta 100 caracteres y contener solo los caracteres A-Z, a-z, y 0-9 y espacios. Los nombres de columna deben ser únicos.
- En el inicio, se pretende permitir columnas de atributo 50.

### <a name="add-bucket-columns"></a>Agregar columnas de cubo

Puede Agregar columnas de cubo para crear cubos, que son agrupaciones en las que se pueden organizar las tareas. Cada cubo obtiene su propia columna en el archivo CSV. Los cubos que cree estarán disponibles para el equipo de publicación. El equipo de publicación puede usar estos cubos para clasificar las tareas para los equipos de los destinatarios. Si aún no existe un cubo en un equipo, los cubos se crean a petición cuando se publican las tareas.

Al clasificar el trabajo una vez de forma centralizada, el equipo de publicación puede organizar previamente la lista de tareas de todos los decenas, cientos o miles de equipos destinatarios que reciben la lista de tareas. Los equipos destinatarios pueden ordenar y filtrar sus tareas por cubos para centrarse en el área más relevante para su trabajo.

Cuando agregue una columna de cubo, tenga en cuenta lo siguiente:

- El nombre de la columna se convierte en el nombre del cubo. Cada depósito que especifique aparecerá en la lista de cubos de las aplicaciones de teams que usan la jerarquía. Le recomendamos que no incluya información confidencial en los nombres de cubo. En este momento, los equipos de publicación no pueden quitar un depósito a través de la publicación después de crearlo.
- El nombre de la columna debe ir precedido de un hashtag (#). Puede tener hasta 100 caracteres y contener solo los caracteres A-Z, a-z y 0-9. Por ejemplo, #Operations y #Frozen bienes.
- En el lanzamiento, esperamos que se admitan 25 columnas de cubo. Tenemos pensado trabajar con clientes para aumentar este límite para organizaciones de mayor tamaño.

### <a name="example"></a>Ejemplo

Este es un ejemplo de un archivo CSV de esquema que se crearía para admitir la jerarquía que se muestra en la imagen de arriba. Este esquema contiene lo siguiente:

- Hay tres columnas `TargetName`obligatorias `ParentName`denominadas, y`TeamID`
- Tres columnas de atributos `Store layout`denominadas, `Departments:Clothing`y`Departments:Foods`
- Tres columnas de cubo `Fresh Foods`denominadas, `Frozen Foods`y`Womenswear`

El `Store layout` atributo tiene valores que incluyen `Compact`, `Standard`, y `Large`. Las `Departments` columnas de atributos pueden establecerse en un valor `0` de (cero) `1`o. El `Store` diseño y `Departments` los atributos no se muestran en la imagen de arriba. Se han agregado aquí para ayudar a mostrar cómo se pueden agregar atributos a las entradas de nodo. Lo mismo sucede con las tres columnas de cubo.


| NombreDeDestino             | ParentName                      | TeamID                       | Diseño de tienda|Departamentos: ropa|Departamentos: alimentos|Alimentos #Fresh|Alimentos #Frozen|#Womenswear|
|------------------------|-------------------------|--------------------------------------|-------------|---|---|---|---|---|
| Recuperar                 |                         | db23e6ba-04a6-412a-95e8-49e5b01943ba |||||||
| Comunicaciones         |                         | 145399ce-a761-4843-a110-3077249037fc |||||||
| RR. HH.                     |                         | b8f7db91-201c-4cf9-9f7e-90a4894ed8e4 |||||||
| Oficina regional del este   |                         |                                      |||||||
| Oficina Regional Occidental   |                         |                                      |||||||
| Zona de noreste        | Oficina regional del este    |                                      |||||||
| Zona de sudeste        | Oficina regional del este    |                                      |||||||
| Tienda de Nueva York         | Zona de noreste         | e2ba65f6-25e7-488b-b8f0-b8562d5de60a |Grande|1|1||||
| Tienda Boston           | Zona de noreste         | 0454f08a-0507-437c-969a-682eb2fae7fc |Standard|1|1||||
| Tienda Miami            | Zona de sudeste         | 619d6e4e-5f68-4b36-8e1f-16c98d7396c1 |ROM|,0|1||||
| Tienda de Nueva Orleans      | Zona de sudeste         | 6be960b8-72af-4561-A343-9ac4711874eb |ROM|,0|1||||
| Tienda de Seattle          | Oficina Regional Occidental    | 487c0d20-4e55-4dc2-8187-a24c826e0fee |Standard|1|1||||
| Tienda de los Angeles      | Oficina Regional Occidental    | 204a1287-2efb-4a8a-88e0-56fbaf5a2389 |Grande|1|1||||

## <a name="apply-your-hierarchy"></a>Aplicar la jerarquía

> [!IMPORTANT]
> Para realizar este paso, debe instalar y usar la última versión del módulo de PowerShell de Teams desde la galería de pruebas de PowerShell. Para conocer los pasos para realizar esto, consulte [instalar el módulo de PowerShell más reciente de la galería de pruebas de PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).

Una vez que haya definido la jerarquía en el archivo CSV de esquema, estará listo para cargarla en Teams. Para ello, ejecute el siguiente comando. Debe ser administrador global o administrador de servicios de equipo para poder realizar este paso.

```powershell
Set-TeamTargetingHierarchy -FilePath "C:\ContosoTeamSchema.csv"
```

## <a name="remove-your-hierarchy"></a>Quitar la jerarquía

> [!IMPORTANT]
> Para realizar este paso, debe instalar y usar la última versión del módulo de PowerShell de Teams desde la galería de pruebas de PowerShell. Para conocer los pasos para realizar esto, consulte [instalar el módulo de PowerShell más reciente de la galería de pruebas de PowerShell](#install-the-latest-teams-powershell-module-from-the-powershell-test-gallery).

Si desea deshabilitar inmediatamente la pestaña **listas publicadas** para todos los usuarios de su organización, puede quitar la jerarquía. Los usuarios no tendrán acceso a la pestaña **listas publicadas** ni a ninguna de las funciones de la ficha.  Esto incluye la capacidad de crear listas de tareas nuevas para publicar, obtener acceso a listas de borradores, publicar, anular la publicación y duplicar listas, así como ver informes. Al quitar la jerarquía, no se anula la publicación de las tareas publicadas anteriormente. Estas tareas seguirán estando disponibles para que se completen los equipos de los destinatarios. 

Para quitar la jerarquía, ejecute el siguiente comando. Debe ser un administrador para poder realizar este paso. 

```powershell
Remove-TeamTargetingHierarchy
```

### <a name="teams-powershell-module"></a>Módulo de PowerShell de Teams

#### <a name="install-the-latest-teams-powershell-module-from-the-powershell-test-gallery"></a>Instale el módulo de PowerShell más reciente de la galería de pruebas de PowerShell

La última versión disponible públicamente del módulo de PowerShell de Teams (actualmente [1.0.5](https://www.powershellgallery.com/packages/MicrosoftTeams/1.0.5)) no admite la administración de la jerarquía del equipo. Siga estos pasos para instalar la última versión del módulo de PowerShell de Teams, con compatibilidad con jerarquía de equipo, de la galería de pruebas de PowerShell.

> [!NOTE]
> No instale el módulo de Teams PowerShell desde la galería de pruebas de PowerShell en paralelo con una versión del módulo de la galería de PowerShell pública. Siga estos pasos para desinstalar primero el módulo de PowerShell de Teams de la galería de PowerShell pública y, a continuación, instale la última versión del módulo desde la galería de pruebas de PowerShell.

1. Cierre todas las sesiones de PowerShell existentes.
2. Inicie una nueva instancia del módulo de Windows PowerShell.
3. Ejecute lo siguiente para desinstalar el módulo de PowerShell de Teams de la galería pública de PowerShell:

    ```PowerShell
    Uninstall-Module -Name MicrosoftTeams
    ```

4. Cierre todas las sesiones de PowerShell existentes.
5. Inicie el módulo de Windows PowerShell de nuevo y, a continuación, ejecute lo siguiente para registrar la galería de pruebas de PowerShell como una fuente de confianza:

    ```PowerShell
    Register-PSRepository -Name PSGalleryInt -SourceLocation https://www.poshtestgallery.com/ -InstallationPolicy Trusted
    ```

6. Ejecute lo siguiente para instalar el módulo de PowerShell más reciente de la galería de pruebas de PowerShell:

    ```PowerShell
    Install-Module -Name MicrosoftTeams -Repository PSGalleryInt -Force
    ```

7. Ejecute lo siguiente para comprobar que se ha instalado correctamente la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

#### <a name="update-to-the-latest-version-of-the-teams-powershell-module-from-the-powershell-test-gallery"></a>Actualice a la última versión del módulo de PowerShell de Teams desde la galería de pruebas de PowerShell

Si ya ha instalado el módulo de Teams PowerShell desde la galería de pruebas de PowerShell, siga estos pasos para actualizar a la última versión.

1. Cierre todas las sesiones de PowerShell existentes.
2. Inicie una nueva instancia del módulo de Windows PowerShell.
3. Ejecute lo siguiente para actualizar la versión del módulo de PowerShell instalada actualmente desde la galería de pruebas de PowerShell:

    ```PowerShell
    Update-Module -Name MicrosoftTeams -Force
    ```

4. Ejecute lo siguiente para comprobar que se ha instalado correctamente la última versión del módulo Teams PowerShell de la galería de pruebas de PowerShell:

    ```PowerShell
    Get-Module -Name MicrosoftTeams
    ```

## <a name="troubleshooting"></a>Solución de problemas

### <a name="you-receive-an-error-message-when-you-upload-your-schema-file"></a>Recibe un mensaje de error al cargar el archivo de esquema

Tome nota del mensaje de error, ya que debe incluir información de solución de problemas para indicar por qué no se pudo cargar el esquema. Revise y edite el archivo CSV de esquema en función de la información del mensaje de error e inténtelo de nuevo.

## <a name="related-topics"></a>Temas relacionados

- [Administrar la aplicación tareas de su organización en Teams](manage-tasks-app.md)
