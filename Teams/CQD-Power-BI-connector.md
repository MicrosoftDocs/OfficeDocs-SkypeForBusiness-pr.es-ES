---
title: Instalar Power BI Connector para usar plantillas de consulta del CQD
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
description: Instalar Power BI Connector para usar plantillas de consulta de panel de calidad de llamadas
ms.openlocfilehash: c3812032f385a3428feec7f1126663e815af1b52
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611584"
---
# <a name="install-power-bi-connector-to-use-cqd-query-templates"></a>Instalar Power BI Connector para usar plantillas de consulta del CQD

Antes de poder usar las plantillas de consulta de Power BI (archivos PBIX) para el panel de calidad de llamadas (CQD) de Microsoft Teams, debe instalar Power BI Connector para Microsoft CQD, con el archivo *MicrosoftCallQuality.pqx* que se incluye en la [descarga.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true)

Lea [Usar Power BI para analizar datos del CQD para Teams para](CQD-Power-BI-query-templates.md) obtener información sobre estas plantillas.

Asegúrese de que tiene el rol de [acceso del CQD correcto](https://docs.microsoft.com/microsoftteams/turning-on-and-using-call-quality-dashboard#assign-roles-for-accessing-cqd) para acceder a los informes de Power BI.

> [!NOTE]
> El conector de Power BI del CQD solo admite DirectQuery en Power BI; El modo de importación no es compatible. 

## <a name="installation"></a>Instalación

El proceso para instalar un conector personalizado y ajustar la seguridad para habilitar el uso del conector se describe en detalle en la [documentación de Power BI.](https://docs.microsoft.com/power-bi/desktop-connector-extensibility) Por simplicidad, aquí tiene una explicación rápida:

1. Compruebe si el equipo ya tiene una carpeta *\[ documentos de \] \\ conectores \\ personalizados de Power BI Desktop.* Si no es así, cree esta carpeta. <sup>1</sup>

2. Descargue el archivo del conector (ya sea un archivo *\* .mez* o *\* .pqx)* y colómelo en el directorio *Conectores personalizados.*

3. **Si el archivo del conector es *\* un archivo .mez,*** también tendrá que ajustar la configuración de seguridad como se describe en la documentación de configuración [personalizada del conector.](https://docs.microsoft.com/power-bi/desktop-connector-extensibility#data-extension-security)

Si se libera una nueva versión de este conector de Power BI para Microsoft Teams, simplemente reemplace el archivo del conector antiguo en el directorio Conectores *personalizados* por el archivo nuevo.

## <a name="setup"></a>Configuración

Para crear un informe y ejecutar consultas, primero debe conectarse al origen de datos del CQD. Siga los pasos siguientes para conectarse:

1. En la pestaña Inicio de Power BI Desktop, haga clic en *Obtener datos.*

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector1-resize.png)

2. En *este momento,* debería aparecer la ventana Obtener datos. Navega a *Servicios en línea,* selecciona *Calidad de llamadas de Microsoft (Beta)* y pulsa *Conectar.*

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector2-resize.png)

3. A continuación, se le pedirá que inicie sesión. Use las mismas credenciales que usa para el CQD. <sup>2</sup>

4. La siguiente pregunta le dará la opción entre dos modos *de conectividad de datos.* Seleccione *DirectQuery y* pulse *Aceptar.*

5. Por último, se le mostrará un mensaje final que le mostrará todo el modelo de datos para el CQD. No se podrán ver datos en este momento, solo el modelo de datos para el CQD. Seleccione *Cargar* para completar el proceso de configuración.

6. En este momento, Power BI cargará el modelo de datos en el lado derecho de la ventana. De lo contrario, la página permanecerá en blanco y no se cargarán consultas de forma predeterminada. Continúe con **el proceso de creación de** consultas a continuación para crear una consulta y devolver datos.

Si alguno de los pasos de este proceso de configuración no estaba completamente claro, encontrará una explicación más detallada del proceso en Inicio rápido: Conectarse a datos en [Power BI Desktop.](https://docs.microsoft.com/power-bi/desktop-quickstart-connect-to-data)

## <a name="building-queries"></a>Creación de consultas

Una vez completada la configuración, debería ver los nombres de varias centenas de dimensiones y carga de medidas en el *panel Campos.* Crear consultas reales desde aquí es sencillo, solo tiene que seleccionar las dimensiones y medidas que desea para la consulta y, a continuación, arrastrarlas y colocarlas en la página. Aquí tiene una explicación más detallada, con un ejemplo sencillo:

1. Seleccione la visualización que desea usar en el *panel Visualizaciones.* Debería aparecer una versión en blanco de esa visualización en la página. Para los fines de este ejemplo, usaremos la visualización *de* tabla.

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector3-resize.png)

2. Determine las dimensiones y medidas (que se indican con un símbolo de agregación por su nombre) que desea usar para la consulta. A continuación, selecciónelos manualmente y arrástrelos hasta la visualización negra. También puede arrastrarlos al campo *Valores debajo* de las opciones de visualización.

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector4-resize2.png)

    > [!IMPORTANT]
    > El panel de calidad de llamadas requiere una medida para que se ejecute cualquier consulta. Si no se agrega una medida a una consulta, se producirá un error en la consulta.

3. A continuación, seleccione las dimensiones que quiera filtrar y arrástrelas a filtros en este *campo visual* en el *panel* Filtros. Actualmente, Power BI Connector del CQD admite el filtrado básico (seleccionar valores de una lista de posibles valores de dimensión), el filtrado avanzado (especificar manualmente  los valores y operandos por los que filtrar, de forma similar al CQD avanzado) y el filtrado de fecha relativo *(solo* disponible para las dimensiones Hora de finalización e Hora de inicio).    El filtrado según *N superior no* es compatible con el CQD.

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector5-resize.png)

4. Por último, seleccione la *pestaña Formato* en el *panel Visualizaciones* para aplicar un estilo y dar formato a la consulta.

    > [!NOTE]
    > Las consultas del CQD requieren al menos una medida para poder ejecutarse. Si la consulta no se carga, compruebe de nuevo que ha incluido una medida en la consulta.

## <a name="creating-a-drillthrough-report"></a>Crear un informe de obtención de detalles

[La obtención de](https://docs.microsoft.com/power-bi/desktop-drillthrough) detalles en Power BI le permite crear informes específicos que puede filtrar rápidamente usando los valores de otros informes como contexto. Una vez que sepa cómo crear su primera consulta con el conector CQD, crear un obtención de detalles es incluso más sencillo.

1. Cree otra página para el informe enfocado y, a continuación, agregue las consultas a esa página.

2. Seleccione la dimensión que desea usar como filtro de  obtención de detalles y arrástrelas hasta el campo Obtención de detalles en el *panel Visualizaciones.*

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector6-resize.png)

3. **Eso es todo\!** Cualquier otra consulta en otra página que use esa dimensión ahora puede obtener obtención de detalles en esa página, aplicando automáticamente el valor de la dimensión de obtención de detalles como filtro.

    ![Captura de pantalla: Power BI Connector](media/CQD-power-bi-connector7-resize.png)

A diferencia del CQD avanzado, Power BI admite la obtención de detalles no secuencial. Siempre que una consulta incluya la dimensión necesaria, podrá obtener acceso a cualquier otra página.

### <a name="best-practice"></a>Procedimientos recomendados

Las consultas de conectores de calidad de llamadas deben diseñarse pensando en la funcionalidad de obtención de detalles. En lugar de intentar cargar todos los datos a la vez y luego cortar los filtros, comience con consultas más amplias de baja cardinalidad y explore en profundidad hasta consultas de alta cardinalidad. Por ejemplo, al intentar diagnosticar las subredes que más contribuyen a los problemas de calidad, resulta útil identificar en primer lugar las regiones y países que contribuyen al problema y, después, explorar en profundidad las subredes de esa región o país. Las plantillas de conectores de calidad de llamadas se han diseñado de esta forma para que actúen como ejemplo.

## <a name="limitations"></a>Limitaciones

A pesar de usar Power BI, no todas las funciones de Power BI son compatibles con el conector CQD, ya sea como consecuencia de las limitaciones del modelo de datos del CQD o de los conectores DirectQuery en general. En la siguiente lista se indican algunas de las limitaciones más destacadas de Conector, pero esta lista no debe considerarse exhaustiva:

1. **Columnas calculadas:** Los conectores de DirectQuery en general tienen compatibilidad limitada para columnas calculadas en Power BI. Aunque algunas columnas calculadas pueden funcionar con el conector, estas deben considerarse excepciones. Como regla general, las columnas calculadas no funcionarán.

2. **Agregaciones:** El modelo de datos del CQD se basa en un modelo de cubo, lo que significa que las agregaciones ya son compatibles con forma de medidas. Intentar agregar agregaciones manualmente a distintas dimensiones o cambiar el tipo de agregación de una medida no funcionará con el conector y, por lo general, producirá un error.

3. **Objetos visuales personalizados:** Aunque el conector CQD funciona con un intervalo de objetos visuales personalizados, no podemos garantizar la compatibilidad con todos los objetos visuales personalizados. Muchos objetos visuales personalizados dependen del uso de columnas calculadas o datos importados, ninguno de los cuales o los que son compatibles con conectores DirectQuery.

4. **Hacer referencia a datos en caché:** Actualmente, Power BI no admite hacer referencia de forma alguna a datos en caché de un conector de DirectQuery. Cualquier intento de hacer referencia a los resultados de una consulta dará como resultado una nueva consulta.

5. **Filtrado de datos relativo:** Es compatible con el conector CQD, pero solo con las dimensiones Hora de inicio y *Hora de* finalización.  Aunque la *dimensión de* fecha puede ser la elección obvia para el filtrado de fecha *relativo,* La fecha no se almacena como un objeto de fecha y, por lo tanto, no admite el filtrado de fecha relativo en Power BI.

6. **Soporte técnico para la nube para la comunidad de la administración pública (GCC):** Para los clientes en el entorno GCC, el conector CQD Power BI funcionará al usar Power BI Desktop. El conector de Power BI del CQD no es compatible actualmente con el servicio Power BI para los clientes de GCC.

La mayoría de estos problemas son restricciones al diseño del conector de DirectQuery en Power BI o son fundamentales para el diseño del modelo de datos del CQD.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="im-trying-to-use-the-date-column-as-a-date-slicer-as-soon-as-i-convert-the-data-type-of-this-column-to-date-i-get-this-error"></a>Estoy intentando usar la columna Fecha como segmentación de datos de fecha. Tan pronto como convierta el tipo de datos de esta columna en Fecha, aparece este error

> **No se pudieron cargar los** datos para este error visual: OLE DB u ODBC: [Expression.Error] No se pudo doblar la expresión al origen de datos. Pruebe una expresión más sencilla.

Las segmentaciones de datos de fecha no son compatibles con Power BI Connector. Para especificar un intervalo de fechas, aplique dos filtros al informe, especificando una fecha menor que y mayor que la fecha.

Como alternativa, si las fechas que desea ver son recientes, aplique un filtro de fecha relativa para mostrar solo los datos de los últimos N días/semanas/meses.

## <a name="error-codes"></a>Códigos de error

Como el conector de Power BI del CQD está menos restringido que la aplicación de explorador en términos de tipos de consultas que puede crear, puede encontrar en ocasiones varios errores al crear las consultas. En caso de que reciba un mensaje de error del tipo "CQDError. RunQuery – Error de ejecución de consulta", haga referencia a la lista siguiente con el número de ErrorType proporcionado para solucionar el posible problema con la consulta. Los siguientes son los códigos de tipo de error más comunes que puede encontrar con el conector Power BI CQD:

- **ErrorType 1 - Error de estructura de consulta:** Un error de estructura de consulta suele deberse a que Connector no crea una consulta con el formato correcto. Esto ocurre la mayoría de las veces cuando se usa una funcionalidad no compatible, como se especifica en las limitaciones anteriores. Compruebe que no está usando ninguna columna calculada o objetos visuales personalizados para esa consulta.

  - **ErrorType 2 - Error de creación de consulta:** Un error de compilación de consulta se debe a que el conector CQD no puede analizar correctamente la consulta que está intentando generar. Esto ocurre la mayoría de las veces cuando se usa una funcionalidad no compatible, como se especifica en las limitaciones anteriores. Compruebe que no está usando ninguna columna calculada o objetos visuales personalizados para esa consulta.

  - **ErrorType 5: tiempo de espera de ejecución:** La consulta ha alcanzado el tiempo de ejecución máximo posible antes de hacer el tiempo de reserva. Intente agregar más filtros a la consulta para limitar su ámbito. Restringir el rango de datos suele ser la forma más eficaz de lograrlo.

  - **Tipo de error 7: error de medición:** Las consultas del CQD requieren una medida para funcionar. Compruebe que la consulta incluye medida. Las medidas del conector CQD se indican con el símbolo de agregación (suma) delante de su nombre.

Si se producen errores adicionales fuera de este ámbito, notifique al equipo de la CQD para que podamos ayudar a solucionar el problema y actualizar la documentación según corresponda.

## <a name="footnotes"></a>Notas al pie

**<sup>1 Determinados</sup>** procesos y aplicaciones (por ejemplo, OneDrive) pueden hacer que cambie la carpeta raíz de documentos; asegúrese de que el *directorio de conectores \\ personalizados de Power BI Desktop* está dentro de la carpeta raíz actual Documentos.

**<sup>2 Las</sup>** credenciales de inicio  de sesión que usa para el CQD no necesitan ser las mismas credenciales que usa para iniciar sesión en la propia aplicación de Escritorio de Power BI.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="when-will-the-power-bi-connector-be-updated-from-beta-status"></a>Cuándo se actualizará Power BI Connector desde el estado "Beta"

A pesar de la etiqueta Beta, el conector de calidad de llamadas para Power BI es la versión de lanzamiento del conector y ha sido firmado oficialmente por el equipo de Power BI para reflejarlo. El proceso de certificación para quitar esa etiqueta Beta es amplio y requiere un compromiso del equipo de Power BI para proporcionar también soporte directo al conector. Debido a las limitaciones de tiempo, el equipo de Power BI no puede proporcionar actualmente ese soporte técnico y una certificación más amplia, pero aún está preparado para garantizar la seguridad, la autenticidad y la funcionalidad general del conector de calidad de llamadas de Microsoft.

### <a name="why-does-the-connector-seem-slower-compared-to-advanced-cqd-in-the-browser-what-can-i-do-to-improve-performance"></a>¿Por qué el conector parece más lento en comparación con el CQD avanzado del explorador? ¿Qué puedo hacer para mejorar el rendimiento?

El rendimiento de las consultas para las distintas plantillas es en realidad el mismo tanto en el explorador como en el conector.  Al igual que con cualquier otra aplicación independiente, Power BI agrega su tiempo de autenticación y representación a nuestro rendimiento. Además, la diferencia está en el número de consultas simultáneas que se están ejecutando. Debido a que la versión en el explorador del CQD tenía opciones de visualización de información menos desarrolladas y con poca densidad de información, la mayoría de los informes se limitaban a cargar de dos a tres consultas a la vez. Por otro lado, las plantillas de conector suelen mostrar más de 20 consultas simultáneas. Si desea crear informes que respondan tan pronto como los antiguos, intente crear informes que no sean más de 2 a 3 consultas por pestaña.

Para obtener más información, vea los artículos siguientes:

- [Guía de optimización de Power BI](https://docs.microsoft.com/power-bi/guidance/power-bi-optimization)
- [Guía del modelo DirectQuery](https://docs.microsoft.com/power-bi/guidance/directquery-model-guidance)

### <a name="i-find-that-i-routinely-run-into-the-10000-row-limit-when-running-queries-how-can-i-get-the-connector-to-return-more-than-10000-rows"></a>Me encuentro con que me encuentro rutinariamente con el límite de 10 000 filas al ejecutar consultas. ¿Cómo puedo conseguir que el conector devuelva más de 10 000 filas?

El límite de 10 000 filas se especifica realmente en el extremo de la API y está diseñado para ayudar a mejorar significativamente el rendimiento y reducir el riesgo de errores de ejecución de consultas resultantes de condiciones de poca memoria.

En lugar de intentar aumentar el recuento de filas de resultados, es mejor volver a estructurar los informes según los procedimientos recomendados del conector. Las plantillas que hemos incluido están diseñadas para demostrar estos procedimientos recomendados. Cuando sea posible, empiece observando los KPI con dimensiones más amplias y de menor cardinalidad, como Mes, Año, Fecha, Región, País, etc. Desde allí, puede explorar en profundidad las dimensiones de mayor cardinalidad. El departamento de soporte técnico y Location-Enhanced informes proporcionan buenos ejemplos de este flujo de trabajo de obtención de detalles.



## <a name="related-topics"></a>Temas relacionados

[Usar Power BI para analizar datos del CQD para Teams](CQD-Power-BI-query-templates.md)
