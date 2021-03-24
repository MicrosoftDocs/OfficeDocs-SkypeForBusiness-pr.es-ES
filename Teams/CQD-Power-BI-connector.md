---
title: Instalar Power BI Connector para usar plantillas de consulta CQD
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Instalar Power BI Connector para usar plantillas de consulta de panel de calidad de llamadas (CQD)
ms.openlocfilehash: 7af8da203eb6a69bf5db443444c0ca35eff9bb70
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51101526"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>Instalar Power BI Connector para usar plantillas de consulta CQD

Antes de poder usar las plantillas de consulta de Power BI (archivos PBIX) para el panel de calidad de llamadas (CQD) de Microsoft Teams, tendrá que instalar Power BI Connector para Microsoft CQD con el archivo *MicrosoftCallQuality.pqx* incluido en la [descarga.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

Lea [Usar Power BI para analizar datos de CQD para Teams](CQD-Power-BI-query-templates.md) para obtener información sobre estas plantillas.

Asegúrese de que tiene el rol de [acceso CQD adecuado](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para obtener acceso a los informes de Power BI.

> [!NOTE]
> El conector de Power BI de CQD solo admite DirectQuery en Power BI; El modo de importación no es compatible. 

## <a name="installation"></a>Instalación

El proceso para instalar un conector personalizado y ajustar la seguridad para habilitar el uso del conector se describe detalladamente en la [documentación de Power BI.](/power-bi/desktop-connector-extensibility) En aras de la sencillez, esta es una explicación rápida:

1. Compruebe si su equipo ya tiene una carpeta *\[ Conectores personalizados de \] \\ Escritorio de Power BI \\ documentos.* Si no es así, cree esta carpeta. <sup>1</sup>

2. Descargue el archivo del conector (ya sea un *\* archivo .mez* o *\* .pqx)* y colócarlo en el *directorio Conectores personalizados.*

3. **Si el archivo del conector es *\* un archivo .mez,*** también tendrá que ajustar la configuración de seguridad como se describe en la documentación de configuración del conector [personalizado.](/power-bi/desktop-connector-extensibility#data-extension-security)

Si se lanza una nueva versión de este Conector de Power BI para Microsoft Teams, simplemente reemplace el archivo de conector antiguo en el directorio *Conectores personalizados* por el nuevo archivo.

## <a name="setup"></a>Configuración

Para crear un informe y ejecutar consultas, primero tendrá que conectarse al origen de datos CQD. Siga los pasos siguientes para conectarse:

1. En la pestaña Inicio de Power BI Desktop, haga clic en *Obtener datos.*

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector1-resize.png)

2. La *ventana Obtener* datos debería aparecer en este momento. Vaya a *Servicios en línea* y, a continuación, seleccione Calidad de llamada de Microsoft *(Beta)* y pulse *Conectar.*

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector2-resize.png)

3. Se le pedirá que inicie sesión a continuación. Use las mismas credenciales que usa para CQD. <sup>2</sup>

4. El siguiente mensaje le dará la opción entre dos modos *de conectividad de datos.* Seleccione *DirectQuery* y pulse *Aceptar*.

5. Por último, se le mostrará un mensaje final que le mostrará todo el modelo de datos para CQD. No se podrá ver ningún dato en este momento, solo el modelo de datos para CQD. Seleccione *Cargar* para completar el proceso de configuración.

6. En este momento, Power BI cargará el modelo de datos en el lado derecho de la ventana. De lo contrario, la página permanecerá en blanco y no se cargarán consultas de forma predeterminada. Vaya a **Crear consultas a** continuación para crear una consulta y devolver datos.

Si alguno de los pasos durante este proceso de configuración no estaba completamente claro, encontrará una explicación más detallada del proceso en Inicio rápido: Conectarse a datos en [Power BI Desktop.](/power-bi/desktop-quickstart-connect-to-data)

## <a name="building-queries"></a>Crear consultas

Una vez completada la configuración, verá los nombres de varios cientos de dimensiones y medidas de carga en el *panel* Campos. Crear consultas reales desde aquí es sencillo, solo tiene que seleccionar las dimensiones y medidas que desee para la consulta y, a continuación, arrastrarlas y colocarlas en la página. Esta es una explicación más detallada, con un ejemplo sencillo:

1. Seleccione la visualización que desea usar en el *panel Visualizaciones.* Una versión en blanco de esa visualización debería aparecer en la página. Para los fines de este ejemplo, usaremos la visualización *Tabla.*

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector3-resize.png)

2. Determine qué dimensiones y medidas (que se indican con un símbolo de agregación por su nombre) que desea usar para la consulta y, a continuación, selecciónelos manualmente y arrástrelos a la visualización negra. Como alternativa, arrástrelos al *campo Valores* debajo de las opciones de visualización.

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > El Panel de calidad de llamadas requiere una medida para que se ejecute cualquier consulta. Si no se agrega una medida a una consulta, se producirá un error en dicha consulta.

3. A continuación, seleccione las dimensiones que quiera filtrar y arrástrelas al campo Filtros de este *campo visual* en el *panel* Filtros. El conector de Power BI CQD admite actualmente filtrado básico (valores de selección de una lista de posibles valores de dimensión), filtrado avanzado (especificar  manualmente  valores y operandos para filtrar, similar a CQD avanzado) y filtrado de fecha relativo *(solo* disponible para las dimensiones Hora de finalización e Hora de inicio).   El filtrado según *N superior no* es compatible con CQD.

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector5-resize.png)

4. Por último, seleccione la *pestaña* Formato en el *panel Visualizaciones* para aplicar estilo y formato a la consulta.

    > [!NOTE]
    > Las consultas de CQD requieren al menos una medida para poder ejecutarse. Si la consulta no se carga, compruebe dos vez que ha incluido una medida en la consulta.

## <a name="creating-a-drillthrough-report"></a>Crear un informe de obtención de detalles

[La obtención de detalles](/power-bi/desktop-drillthrough) en Power BI le permite crear informes centrados que puede filtrar rápidamente con los valores de otros informes como contexto. Una vez que sepa cómo crear la primera consulta con el conector CQD, la creación de una obtención de detalles es incluso más sencilla.

1. Cree otra página para el informe centrado y, a continuación, agregue las consultas a esa página.

2. Seleccione la dimensión que desea usar como filtro de obtención de detalles y arrástrela al campo *Obtención* de detalles en el *panel Visualizaciones.*

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector6-resize.png)

3. **Eso es todo\!** Cualquier otra consulta de otra página que use esa dimensión ahora puede obtener detalles de esa página, aplicando automáticamente el valor de la dimensión de obtención de detalles como filtro.

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector7-resize.png)

A diferencia de CQD avanzado, Power BI admite la obtención de detalles no secuencial. Siempre que una consulta incluya la dimensión necesaria, puede obtener detalles en cualquier otra página.

### <a name="best-practice"></a>Procedimientos recomendados

Las consultas de conector de calidad de llamadas deben diseñarse pensando en la funcionalidad de obtención de detalles. En lugar de intentar cargar todos los datos a la vez y, a continuación, cortar con filtros, empiece con consultas más amplias y de baja cardinalidad y explore en profundidad las consultas de alta cardinalidad. Por ejemplo, al intentar diagnosticar qué subredes contribuyen más a los problemas de calidad, es útil identificar primero aquellas regiones y países que contribuyen al problema y, después, explorar en profundidad las subredes de esa región o país. Las plantillas de conector de calidad de llamada se han diseñado de esta manera para actuar como un ejemplo.

## <a name="limitations"></a>Limitaciones

A pesar de usar Power BI, no todas las funciones de Power BI son compatibles con el conector CQD, ya sea como resultado de limitaciones en el modelo de datos CQD o en conectores de DirectQuery en general. En la lista siguiente se indican algunas de las limitaciones más destacadas del Conector, pero esta lista no debe considerarse exhaustiva:

1. **Columnas calculadas:** Los conectores de DirectQuery en general tienen compatibilidad limitada para columnas calculadas en Power BI. Aunque algunas columnas calculadas pueden funcionar con el Conector, estas deben considerarse excepciones. Como regla general, las columnas calculadas no funcionarán.

2. **Agregaciones:** El modelo de datos CQD se basa en un modelo de cubo, lo que significa que las agregaciones ya son compatibles en forma de medidas. Intentar agregar agregaciones manualmente a distintas dimensiones o cambiar el tipo de agregación de una medida no funcionará con el conector y, por lo general, producirá un error.

3. **Objetos visuales personalizados:** Aunque el conector CQD funciona con una amplia variedad de objetos visuales personalizados, no podemos garantizar la compatibilidad con todos los objetos visuales personalizados. Muchos objetos visuales personalizados se basan en el uso de columnas calculadas o datos importados, ninguno o que son compatibles con conectores de DirectQuery.

4. **Hacer referencia a datos almacenados en caché:** Actualmente, Power BI no admite hacer referencia a datos almacenados en caché desde un conector de DirectQuery de ninguna manera. Cualquier intento de hacer referencia a los resultados de una consulta dará como resultado una nueva consulta.

5. **Filtrado de datos relativos:** Es compatible con el conector CQD, pero solo con las dimensiones *Hora de* inicio y Hora *de* finalización. Aunque la *dimensión* Fecha puede ser la opción obvia para el filtrado de fecha relativo, *Fecha* no se almacena como un objeto de hora de fecha y, por lo tanto, no admite el filtrado de fecha relativo en Power BI.

6. Compatibilidad con la nube de la comunidad gubernamental **(GCC):** Para los clientes del entorno GCC, el conector CQD Power BI funcionará al usar Power BI Desktop. El conector CQD Power BI es compatible con el servicio Power BI para los clientes de GCC.

La mayoría de estos problemas son restricciones al diseño de conectores de DirectQuery en Power BI o fundamentales para el diseño del modelo de datos CQD.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Estoy intentando usar la columna Fecha como segmentación de datos de fecha. Tan pronto como convierta el tipo de datos de esta columna en Fecha, aparece este error

> **No se pudieron cargar los** datos de este objeto visual: error OLE DB u ODBC: [Expresión.Error] No se pudo plegar la expresión al origen de datos. Pruebe una expresión más sencilla.

Las segmentaciones de datos no son compatibles con Power BI Connector. Para especificar un intervalo de fechas, aplique dos filtros al informe, especificando una fecha menor y mayor que la fecha.

Como alternativa, si las fechas que desea ver son recientes, aplique un filtro de fecha relativa para mostrar solo los datos de los últimos N días/semanas/meses.

## <a name="error-codes"></a>Códigos de error

Dado que el conector de Power BI de CQD está menos restringido que la aplicación del explorador en términos de tipos de consultas que puede crear, es posible que en ocasiones encuentre una serie de errores al crear las consultas. En el caso de que reciba un mensaje de error del tipo "CQDError. RunQuery: error de ejecución de consulta", haga referencia a la lista siguiente con el número ErrorType proporcionado para solucionar el posible problema con la consulta. Estos son los códigos de tipo de error más comunes que puede encontrar con el conector CQD Power BI:

- **ErrorType 1: error de estructura de consulta:** Normalmente, un error de estructura de consulta se debe a que el conector no puede crear una consulta con el formato adecuado. Esto ocurre con mayor frecuencia al usar funciones no admitidas, como se especifica en las limitaciones anteriores. Compruebe que no usa columnas calculadas ni objetos visuales personalizados para esa consulta.

  - **ErrorType 2: error de creación de consultas:** Un error de creación de consultas se debe a que el conector CQD no puede analizar correctamente la consulta que intenta crear. Esto ocurre con mayor frecuencia al usar funciones no admitidas, como se especifica en las limitaciones anteriores. Compruebe que no usa columnas calculadas ni objetos visuales personalizados para esa consulta.

  - **ErrorType 5: tiempo de espera de ejecución:** La consulta ha alcanzado el tiempo de ejecución máximo posible antes de que se desatrase el tiempo de ejecución. Intente agregar más filtros a la consulta para limitar su ámbito. Restringir el rango de datos suele ser la forma más eficaz de lograrlo.

  - **ErrorType 7: sin errores de medida:** Las consultas CQD requieren una medida para funcionar. Compruebe dos vez que la consulta incluye medida. Las medidas del conector CQD se indican mediante el símbolo de agregación (suma) antes de su nombre.

Si encuentra errores adicionales fuera de este ámbito, notifique al equipo de CQD para que podamos ayudar a solucionar el problema y actualizar la documentación según corresponda.

## <a name="footnotes"></a>Notas al pie

**<sup>1</sup>** Algunos procesos y aplicaciones (por ejemplo, OneDrive) pueden hacer que la carpeta raíz documentos cambie; asegúrese de que el directorio *Conectores \\ personalizados* de Escritorio de Power BI se coloca dentro de la carpeta raíz actual Documentos.

**<sup>2</sup>** Las credenciales de inicio de sesión que usa para CQD *no* necesitan ser las mismas que usa para iniciar sesión en la propia aplicación de escritorio de Power BI.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>¿Cuándo se actualizará Power BI Connector desde el estado "Beta"

A pesar de la etiqueta Beta, el Conector de calidad de llamada para Power BI es la versión de lanzamiento del conector y ha sido firmado oficialmente por el equipo de Power BI para reflejar esto. El proceso de certificación para quitar esa etiqueta beta es amplio y requiere un compromiso del equipo de Power BI para proporcionar soporte directo al conector también. Debido a las limitaciones de tiempo, el equipo de Power BI no puede proporcionar actualmente ese soporte técnico y una certificación más amplia, pero todavía está preparado para dar fe de la seguridad, autenticidad y funcionalidad general del conector de calidad de llamadas de Microsoft.

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a>¿Por qué el conector parece más lento en comparación con CQD avanzado en el explorador? Qué puedo hacer para mejorar el rendimiento

El rendimiento de las consultas para las distintas plantillas es en realidad el mismo en el explorador y en el conector.  Al igual que cualquier otra aplicación independiente, Power BI agrega su tiempo de autenticación y representación a nuestro rendimiento. Además, la diferencia se produce en el número de consultas simultáneas que se ejecutan. Como la versión en el explorador de CQD tenía opciones de visualización menos desarrolladas y densas de información, la mayoría de nuestros informes se limitaban a cargar de 2 a 3 consultas a la vez. Por otro lado, las plantillas de conector suelen mostrar más de 20 consultas simultáneas. Si desea crear informes que respondan igual que los antiguos a los que estaba acostumbrado, intente crear informes con no más de 2 o 3 consultas por pestaña.

Para obtener más información, vea los artículos siguientes:

- [Guía de optimización de Power BI](/power-bi/guidance/power-bi-optimization)
- [Guía del modelo DirectQuery](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Encuentro que rutinariamente me encuentro con el límite de 10 000 filas al ejecutar consultas. ¿Cómo puedo conseguir que el conector devuelva más de 10 000 filas?

El límite de 10 000 filas se especifica realmente en el extremo de la API y está diseñado para ayudar a mejorar significativamente el rendimiento y reducir el riesgo de errores de ejecución de consultas como resultado de condiciones de memoria bajas.

En lugar de intentar aumentar el recuento de filas de resultados, es mejor reorganizar los informes según los procedimientos recomendados del conector. Las plantillas que hemos incluido están diseñadas para demostrar estos procedimientos recomendados. Cuando sea posible, empiece por ver sus KPI con dimensiones más amplias y de menor cardinalidad, como Mes, Año, Fecha, Región, País, etc. Desde allí, puede explorar en profundidad las dimensiones de mayor cardinalidad. Tanto el Departamento de soporte técnico como Location-Enhanced informes proporcionan buenos ejemplos de este flujo de trabajo de exploración en profundidad.



## <a name="related-topics"></a>Temas relacionados

[Usar Power BI para analizar datos CQD para Teams](CQD-Power-BI-query-templates.md)
