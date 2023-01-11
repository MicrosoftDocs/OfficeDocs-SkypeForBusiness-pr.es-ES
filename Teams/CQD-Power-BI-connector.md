---
title: Instalar Power BI Connector para usar plantillas de consulta del CQD
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
description: Instalar Power BI Connector para usar las plantillas de consulta del Panel de calidad de llamadas
ms.openlocfilehash: 534103fc2bec48566a1d0a57eeb390ed6ae0606c
ms.sourcegitcommit: 66d8e3d7a29a03c5deba9780964bc03f6587017f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2023
ms.locfileid: "69774755"
---
# <a name="install-microsoft-call-quality-connector-for-power-bi-to-use-call-quality-dashboard-query-templates"></a>Instalar el conector de calidad de llamadas de Microsoft para Power BI para usar plantillas de consulta del panel de calidad de llamadas

Para poder usar las plantillas de consulta de Power BI (archivos PBIX) para el Panel de calidad de llamadas (CQD) de Microsoft Teams, tendrá que instalar el conector de calidad de llamadas de Microsoft para Power BI con el archivo *MicrosoftCallQuality.pqx* incluido en la [descarga](https://www.microsoft.com/download/details.aspx?id=102291).

Lea [Usar Power BI para analizar datos del CQD para Teams para](CQD-Power-BI-query-templates.md) obtener información sobre estas plantillas.

Asegúrese de que tiene el [rol de acceso correcto del CQD](./turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para obtener acceso a los informes de Power BI.

> [!NOTE]
> El conector De calidad de llamada de Microsoft solo admite DirectQuery en Power BI; El modo de importación no es compatible. 

## <a name="installation"></a>Instalación

El proceso para instalar un conector personalizado y ajustar la seguridad para habilitar el uso del conector se describe detalladamente en la [documentación de Power BI](/power-bi/desktop-connector-extensibility). Por motivos de simplicidad, esta es una breve explicación:

1. Compruebe si su equipo ya tiene una *\[carpeta Documents\]\\ Power BI Desktop\\ Custom Connectors*. Si no es así, cree esta carpeta. <sup>1</sup>

2. Descargue el archivo del conector (un *\*archivo .mez* o *\*.pqx* ) y colócolo en el directorio *Conectores personalizados* .

3. **Si el archivo del conector es un *\*archivo .mez* ,** también tendrá que ajustar la configuración de seguridad como se describe en la [documentación de configuración personalizada del conector](/power-bi/desktop-connector-extensibility#data-extension-security).

Si se publica una nueva versión del conector De calidad de llamada de Microsoft, reemplace el archivo anterior del conector en el directorio *Conectores personalizados* por el nuevo archivo.

## <a name="setup"></a>Configuración

Para crear un informe y ejecutar las consultas, primero necesitará conectarse al origen de datos del CQD. Siga los pasos siguientes para conectarse:

1. En la pestaña Inicio de Power BI Desktop, haga clic en *Obtener datos*.

    ![Obtenga datos en Power BI Connector.](media/CQD-power-bi-connector1-resize.png)

2. La ventana *Obtener datos* debería aparecer en este momento. Vaya a *Servicios en línea*, seleccione *Calidad de llamada de Microsoft (Beta)* y pulse *Conectar*.

    ![Calidad de llamadas de Microsoft en Power BI Connector.](media/CQD-power-bi-connector2-resize.png)

3. Se le pedirá que inicie sesión a continuación. Use las mismas credenciales que usa para el panel de calidad de llamadas. <sup>2</sup>

4. El siguiente aviso le dará la opción entre dos *modos de conectividad de datos*. Seleccione *DirectQuery* y pulse *Aceptar*.

5. Por último, se le mostrará un mensaje final que le mostrará todo el modelo de datos para el panel de calidad de llamadas. No habrá datos visibles en este momento, solo el modelo de datos para el CQD. Seleccione *Cargar* para completar el proceso de configuración.

6. En este punto, Power BI cargará el modelo de datos en el lado derecho de la ventana. De lo contrario, la página permanecerá en blanco y no se cargarán consultas de forma predeterminada. Continúe **con La creación de consultas** a continuación con el fin de crear una consulta y devolver datos.

Si alguno de los pasos durante este proceso de configuración no estaba claro, puede encontrar una explicación más detallada del proceso en [Inicio rápido: Conectarse a los datos de Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

## <a name="building-queries"></a>Consultas de creación

Una vez completada la configuración, debería ver los nombres de varios cientos de dimensiones y la carga de medidas en el panel *Campos* . Construir consultas reales desde aquí es sencillo, solo tiene que seleccionar las dimensiones y medidas que desee para la consulta y arrastrarlas y colocarlas en la página. Esta es una explicación más detallada, con un ejemplo sencillo:

1. Seleccione la visualización que desea usar en el panel *Visualizaciones* . Debería aparecer una versión en blanco de esa visualización en la página. Para los fines de este ejemplo, usaremos la visualización *de tabla* .

    ![Panel Visualizaciones en Power BI Connector.](media/CQD-power-bi-connector3-resize.png)

2. Determine las dimensiones y medidas (indicadas por un símbolo de agregación por su nombre) que desea usar para la consulta, selecciónelas manualmente y arrástrelas a la visualización negra. Como alternativa, arrástrelos hasta el campo *Valores* debajo de las opciones de visualización.

    ! Consulta de visualizaciones en Power BI Connector.] (medios/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > El panel de calidad de llamadas requiere una medida para que cualquier consulta se ejecute. Si no se agrega una medida a una consulta, se producirá un error en esa consulta.

3. A continuación, seleccione las dimensiones por las que quiera filtrar y arrástrelas hasta el campo *de filtros de este campo visual* en el panel *Filtros* . El conector de Calidad de llamada de Microsoft admite actualmente *el filtrado básico* (seleccionar valores de una lista de posibles valores de dimensión), el *filtrado avanzado* (especificar manualmente valores y operandos para filtrar, de forma similar a panel de calidad de llamadas) y el *filtrado de fecha relativo* (solo disponible para las dimensiones *Hora de finalización* y Hora de *inicio* ). El panel de calidad de llamadas no admite el filtrado según *N superior* .

    ![Filtros de visualización en Power BI Connector.](media/CQD-power-bi-connector5-resize.png)

    > [!IMPORTANT]
    > Los filtros solo se admiten cuando se aplican a dimensiones. El filtrado de los valores de Medidas no se admite en el panel de calidad de llamadas.

4. Por último, seleccione la pestaña *Formato* en el panel *Visualizaciones* para dar estilo a la consulta y darle formato.

    > [!NOTE]
    > Las consultas del panel de calidad de llamadas requieren al menos una medida para poder ejecutarse. Si la consulta no se carga, compruebe que ha incluido una medida en la consulta.

## <a name="creating-a-drillthrough-report"></a>Crear un informe de obtención de detalles

[La obtención de detalles en Power BI](/power-bi/desktop-drillthrough) le permite crear informes enfocados que puede filtrar rápidamente usando los valores de otros informes como contexto. Una vez que sepa cómo crear su primera consulta con el conector Calidad de llamada de Microsoft, crear un obtención de detalles es aún más sencillo.

1. Cree otra página para el informe prioritario y, después, agregue las consultas a esa página.

2. Seleccione la dimensión que desea usar como filtro de obtención de detalles y arrástrelas hasta el campo *Obtención de detalles* en el panel *Visualizaciones* .

    ![Obtención de detalles en Power BI Connector.](media/CQD-power-bi-connector6-resize.png)

3. **Eso es todo\!** Cualquier otra consulta de otra página que use esa dimensión ahora puede explorar en profundidad esa página, aplicando automáticamente el valor de la dimensión de obtención de detalles como filtro.

    ![Filtro de obtención de detalles en Power BI Connector.](media/CQD-power-bi-connector7-resize.png)

A diferencia del panel de calidad de llamadas, Power BI admite la obtención de detalles no secuencial. Si una consulta incluye la dimensión necesaria, puede explorar en profundidad cualquier otra página.

### <a name="best-practice"></a>Procedimiento recomendado

Las consultas del conector de calidad de llamadas de Microsoft deben diseñarse teniendo en cuenta la funcionalidad de obtención de detalles. En lugar de intentar cargar todos los datos a la vez y luego reducirlos con filtros, empiece con consultas de cardinalidad baja y más amplias y profundice en consultas de alta cardinalidad. Por ejemplo, al intentar diagnosticar las subredes que más contribuyen a los problemas de calidad, resulta útil identificar primero las regiones y los países que contribuyen al problema y luego explorar en profundidad las subredes de esa región o país. Las plantillas de conector calidad de llamada se han diseñado de esta manera para actuar como ejemplo.

## <a name="limitations"></a>Limitaciones

A pesar de hacer uso de Power BI, no todas las funciones de Power BI son compatibles con el conector de calidad de llamadas de Microsoft, ya sea como resultado de las limitaciones en el modelo de datos del panel de calidad de llamadas o en los conectores DirectQuery en general. La siguiente lista toma nota de algunas de las limitaciones más importantes de Connector, pero esta lista no debe considerarse exhaustiva:

1. **Columnas calculadas:** Los conectores DirectQuery en general tienen compatibilidad limitada con las columnas calculadas en Power BI. Algunas columnas calculadas pueden funcionar con el conector, ya que esas columnas son excepciones. Como regla general, las columnas calculadas no funcionan.

2. **Agregaciones–** El modelo de datos del panel de calidad de llamadas se basa en un modelo de cubo, lo que significa que las agregaciones ya se admiten en forma de medidas. Intentar agregar agregaciones manualmente a distintas dimensiones o cambiar el tipo de agregación de una medida no funcionará con el conector y, por lo general, producirá un error.

3. **Objetos visuales personalizados:** Aunque el conector calidad de llamada de Microsoft funciona con una amplia gama de objetos visuales personalizados, no podemos garantizar la compatibilidad con todos los objetos visuales personalizados. Muchos objetos visuales personalizados se basan en el uso de columnas calculadas o datos importados, ninguno de los cuales es compatible con conectores DirectQuery.

4. **Referencia a datos en caché:** Actualmente, Power BI no admite hacer referencia a los datos almacenados en caché de un conector DirectQuery de ninguna manera. Cualquier intento de hacer referencia a los resultados de una consulta dará como resultado una nueva consulta.

5. **Filtrado de datos relativos:** Es compatible con el conector Calidad de llamada de Microsoft, pero solo con las dimensiones *Hora de inicio* y *Hora de finalización* . Aunque la dimensión *Fecha* puede ser la opción más obvia para el filtrado de fecha relativa, *Date* no se almacena como un objeto de fecha y hora y, por lo tanto, no admite el filtrado de fecha relativo en Power BI.

6. **Consultas solo de medida:** No se admiten en este momento en el conector De calidad de llamada de Microsoft. Al crear una visualización con tres o más medidas y sin dimensiones, los datos de columna se transponen. Para evitar esto, incluya siempre al menos una dimensión (por ejemplo, Month Year) en las visualizaciones. Esto está programado para resolverse en una próxima versión del conector de calidad de llamadas de Microsoft para Power BI.

7. **Soporte técnico de Government Community Cloud (GCC):** Para los clientes en el entorno GCC, el conector de calidad de llamada de Microsoft funcionará solo al usar Power BI Desktop. El conector de calidad de llamada de Microsoft no es compatible actualmente con la servicio Power BI para los clientes de GCC.

La mayoría de estos problemas son restricciones al diseño del conector DirectQuery en Power BI o fundamentales para el diseño del modelo de datos del CQD.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Estoy intentando usar la columna Fecha como segmentación de datos de fecha. Tan pronto como convierte el tipo de datos de esta columna en Fecha, recibo este error

> **No se han podido cargar los datos para este objeto visual**: Error OLE DB u ODBC: [Expresión.Error] No se pudo doblar la expresión al origen de datos. Prueba una expresión más sencilla.

Las segmentaciones de datos de fecha no son compatibles con el conector De calidad de llamada de Microsoft. Para especificar un intervalo de fechas, aplique dos filtros al informe, especificando una fecha menor que y mayor que.

Como alternativa, si las fechas que desea ver son recientes, aplique un filtro de fecha relativo para mostrar solo los datos de los últimos N días/semanas/meses.


### <a name="when-i-add-certain-dimensions-to-my-reports-the-visual-immediately-returns-couldnt-load-the-data-for-this-visual-removing-the-dimension-fixes-the-visual----what-is-happening"></a>Cuando agregue determinadas dimensiones a mis informes, el objeto visual devuelve inmediatamente **"No se pudieron cargar los datos para este objeto visual"**. Quitar la dimensión corrige el objeto visual: ¿qué sucede?

Este es un problema conocido en el conector De calidad de llamada de Microsoft; cualquier dimensión que se exponga como un número completo aparecerá en Power BI como una columna de "agregado", donde Power BI intentará una acción de resumen predeterminada (normalmente "Suma"). En algunos casos, este comportamiento sumará correctamente los valores aunque el resultado no sea útil, ya que la "suma" de una dimensión como el segundo canal Wi-Fi no tiene sentido. En otros casos, esta acción de resumen producirá errores y errores en el objeto visual.

Para solucionar este problema, empiece quitando la dimensión del objeto visual. Seleccione la dimensión en la lista "Campos", vaya a la pestaña "Herramientas de columna" en la cinta de opciones, haga clic en el menú desplegable "Resumen" y seleccione **No resumir**. Ahora, la dimensión se puede volver a agregar al objeto visual.


## <a name="error-codes"></a>Códigos de error

Dado que el conector de calidad de llamadas de Microsoft para Power BI está menos restringido que la aplicación del explorador en términos de tipos de consultas que puede construir, en ocasiones puede encontrar varios errores al crear las consultas. En el caso de que reciba un mensaje de error del tipo "CQDError. RunQuery – Query Execution Error", haga referencia a la siguiente lista con el número ErrorType proporcionado para solucionar el posible problema con la consulta. A continuación se muestran los códigos de tipo de error más comunes que puede encontrar con el conector CQD Power BI:

- **Tipo de error 1 - Error de estructura de consulta:** Un error de estructura de consulta suele deberse a que el conector no puede crear una consulta con el formato correcto. Esto sucede con mayor frecuencia cuando se usa la funcionalidad no compatible, como se especifica en las Limitaciones anteriores. Compruebe que no está usando ninguna columna calculada ni objetos visuales personalizados para esa consulta.

  - **Tipo de error 2: error de compilación de consulta:** Un error de compilación de consultas se debe a que el conector de calidad de llamada de Microsoft no puede analizar correctamente la consulta que intenta crear. Esto sucede con mayor frecuencia cuando se usa la funcionalidad no compatible, como se especifica en las Limitaciones anteriores. Compruebe que no está usando ninguna columna calculada ni objetos visuales personalizados para esa consulta.

  - **Tipo de error 5 - Tiempo de espera de ejecución:** La consulta ha alcanzado el tiempo de ejecución máximo posible antes de agotar el tiempo de espera. Intente agregar más filtros a la consulta para limitar su ámbito. Restringir el rango de datos suele ser la forma más eficaz de lograrlo.

  - **Tipo de error 7 - Error sin medidas:** Las consultas del panel de calidad de llamadas requieren una medida para funcionar. Compruebe que la consulta incluye medidas. Las medidas del conector De calidad de llamada de Microsoft se indican mediante el símbolo de agregación (suma) antes de su nombre.

Si encuentra algún error adicional fuera de este ámbito, notifique al equipo del panel de calidad de llamadas para que podamos ayudar a solucionar el problema y actualizar la documentación según corresponda.

## <a name="footnotes"></a>Notas

**<sup>1</sup>** Determinados procesos y aplicaciones (por ejemplo, OneDrive) pueden hacer que su carpeta raíz Documentos cambie; asegúrese de que el directorio *Power BI Desktop\\ Custom Connectors* se coloca dentro de la carpeta raíz actual Documentos.

**<sup>2</sup>** *No es necesario* que las credenciales de inicio de sesión que use para el panel de calidad de llamadas sean las mismas que usa para iniciar sesión en la propia aplicación Power BI Desktop.

## <a name="frequently-asked-questions"></a>Preguntas más frecuentes

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>¿Cuándo se actualizará Power BI Connector desde el estado "Beta"?

A pesar de la etiqueta Beta, el conector de Calidad de llamadas (Beta) de Microsoft para Power BI es la primera versión de "lanzamiento" del conector y ha sido firmado oficialmente por el equipo de Power BI para reflejarlo. En el momento de la versión inicial del conector, el equipo de Power BI no pudo proporcionar soporte técnico y una certificación más amplia, pero aún estaba preparado para atestiguar la seguridad, la autenticidad y la funcionalidad general del conector De calidad de llamada de Microsoft. De cara al futuro, tenemos previsto invertir en el conector de calidad de llamadas de Microsoft para Power BI en un futuro próximo.

### <a name="why-does-the-connector-seem-slower-compared-to-call-quality-dashboard-in-the-browser-what-can-i-do-to-improve-performance"></a>¿Por qué el conector parece más lento en comparación con el panel de calidad de llamadas en el explorador? ¿Qué puedo hacer para mejorar el rendimiento?

El rendimiento de las consultas para las distintas plantillas es en realidad el mismo tanto en el explorador como en el conector.  Al igual que cualquier otra aplicación independiente, Power BI agrega su tiempo de autenticación y representación a nuestro rendimiento. Además, la diferencia se produce en el número de consultas simultáneas que se ejecutan. Dado que la versión en el explorador del panel de calidad de llamadas tenía menos opciones de visualización bien desarrolladas y densas de información, la mayoría de nuestros informes se limitaban a cargar de 2 a 3 consultas a la vez. Por otro lado, las plantillas de conector suelen mostrar más de 20 consultas simultáneas. Si desea crear informes que respondan igual que los anteriores, intente crear informes con no más de 2 o 3 consultas por pestaña.

Para obtener más información, vea los artículos siguientes:

- [Guía de optimización para Power BI](/power-bi/guidance/power-bi-optimization)
- [Instrucciones del modelo de DirectQuery](/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Me doy cuenta de que encuentro habitualmente el límite de 10 000 filas al ejecutar consultas. ¿Cómo puedo hacer que el conector devuelva más de 10 000 filas?

El límite de 10 000 filas se especifica realmente en el extremo de la API y está diseñado para ayudar a mejorar significativamente el rendimiento y reducir el riesgo de errores de ejecución de consultas resultantes de condiciones de poca memoria.

En lugar de intentar aumentar el recuento de filas de resultados, es mejor reestructurar los informes según los procedimientos recomendados del conector. Las plantillas que hemos incluido están diseñadas para demostrar estos procedimientos recomendados. Cuando sea posible, empiece por ver los KPI con dimensiones más amplias y de menor cardinalidad, como Mes, Año, Fecha, Región, País, etc. Desde allí, puede explorar en profundidad las dimensiones cada vez más altas de cardinalidad. El departamento de soporte técnico y los informes de Location-Enhanced proporcionan buenos ejemplos de este flujo de trabajo de exploración en profundidad.



## <a name="related-topics"></a>Temas relacionados

[Usar Power BI para analizar datos del CQD para Teams](CQD-Power-BI-query-templates.md)
