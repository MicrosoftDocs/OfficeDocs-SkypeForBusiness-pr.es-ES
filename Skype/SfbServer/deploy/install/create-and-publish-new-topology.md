---
title: Creación y publicación de una nueva topología en Skype Empresarial Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 451c41a1-b8c5-4dc3-9e48-0da9ed5381a1
description: 'Resumen: obtenga información sobre cómo crear, publicar y comprobar una nueva topología antes de instalar Skype Empresarial Server.'
ms.openlocfilehash: 9ae6ee05a20f75946a87e611e972341094a11864
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860561"
---
# <a name="create-and-publish-new-topology-in-skype-for-business-server"></a>Creación y publicación de una nueva topología en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo crear, publicar y comprobar una nueva topología antes de instalar Skype Empresarial Server.
  
Para poder instalar el sistema de Skype Empresarial Server en cada uno de los servidores de la topología, debe crear una topología y publicarla. Al publicar una topología, se carga la información de la topología en la base de datos del Almacén de administración central. Si se trata de un grupo de Enterprise Edition, va a crear la base de datos del Almacén de administración central la primera vez que publique una nueva topología. Si esto es Standard Edition, tendrá que ejecutar el proceso Preparar primero Standard Edition server desde el Asistente para la implementación antes de publicar una topología. Esto se prepara para Standard Edition instalando una instancia de SQL Server Express Edition y creando el Almacén de administración central. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, como se describe en el diagrama. En el paso 6 de 8 se describe cómo crear y publicar una nueva topología.
  
![Diagrama de información general.](../../media/c5c09ba2-c98b-4194-9857-7c3087c5560e.png)
  
## <a name="create-and-publish-new-topology"></a>Crear y publicar nueva topología

Puede usar Skype Empresarial Server Generador de topologías para diseñar, definir, configurar y publicar topologías. Esta herramienta se instaló cuando instaló Herramientas administrativas anteriormente en el artículo. Hay muchas opciones diferentes que puede tomar al crear una topología. En este procedimiento, creará una topología básica con conferencias.
  
> [!IMPORTANT]
> Skype Empresarial Server requiere SQL Server para poder operar. Las bases de datos principales se conocen como almacén de administración central. Si va a implementar Enterprise Edition, estas bases de datos se crean al publicar la topología mediante los pasos siguientes. En este caso, el Generador de topologías le pedirá la información de conexión a una instalación de SQL Server. Si tiene previsto implementar Standard Edition, deberá instalar SQL Server Express Edition antes de definir y publicar la nueva topología. Para instalar SQL Server Express Edition, debe abrir el Asistente para implementación en el servidor que actuará como front-end y, a continuación, ejecutar Prepare First Standard Edition Server. Al hacer clic en Preparar el primer Standard Edition Server, el Asistente para la implementación instala automáticamente SQL Server Express Edition y crea las bases de datos del Almacén de administración central. 
  
### <a name="create-a-new-topology"></a>Creación de una nueva topología

1. Inicie sesión como usuario estándar con acceso al Generador de topologías.
    
2. Abra Skype Empresarial Server Generador de topologías.
    
3. Seleccione **Nueva topología** y haga clic en **Aceptar**.
    
4. Seleccione una ubicación y un nombre de archivo para el archivo de configuración de topología.
    
    > [!NOTE]
    > La configuración de la topología se guarda como un archivo XML del Generador de topologías (.tbxml). Al publicar una topología, inserta la información de configuración del archivo en la base de datos SQL Server. Al abrir el Generador de topologías en el futuro, puede descargar la configuración existente de SQL Server directamente en el Generador de topologías y volver a publicarla en SQL Server o guardarla como un archivo de configuración del Generador de topologías. 
  
5. En la **pantalla Definir el dominio principal**, escriba el **dominio SIP principal** y haga clic en **Siguiente**. En este ejemplo, se usa `contoso.local`, como se muestra en la ilustración.
    
     ![Defina el dominio sip principal.](../../media/353e6b38-485f-4042-8585-aefa6c74b554.png)
  
6. Agregue los dominios SIP admitidos adicionales y, a continuación, haga clic en **Siguiente**.
    
7. Escriba un **nombre** y **una descripción** para el primer sitio (ubicación) y, a continuación, haga clic en **Siguiente**, como se muestra en la ilustración.
    
     ![Defina el primer sitio (ubicación).](../../media/d8b6c54a-2011-4efb-97fb-a4de0f11303c.png)
  
8. Escriba la **ciudad**, **el estado o la provincia** y el **código de país o región** del sitio y, a continuación, haga clic en **Siguiente**.
    
9. Haga clic en **Finalizar** para completar el proceso de definición de una nueva topología. El Asistente para nuevo front-end se inicia automáticamente.
    
### <a name="define-a-front-end-pool-or-standard-edition-server"></a>Definir un grupo de servidores front-end o un servidor Standard Edition

1. Revise los requisitos previos del asistente y haga clic en **Siguiente**.
    
2. Escriba el nombre de dominio completo (FQDN) del grupo, seleccione **Enterprise Edition grupo de servidores front-end** o **Standard Edition server** y, a continuación, haga clic en **Siguiente**, como se muestra en la ilustración.
    
    > [!TIP]
    > Skype Empresarial Server Enterprise Edition puede incluir varios servidores que trabajan juntos para proporcionar el rol front-end. Cuando se usan varios servidores para cumplir el rol, se denomina grupo. Por lo tanto, varios servidores que trabajan juntos para proporcionar el rol front-end también se conocen como grupo de servidores front-end. Skype Empresarial Server Standard Edition solo puede incluir un único servidor para proporcionar el rol front-end. Es habitual hacer referencia al grupo de servidores front-end aunque solo un único servidor proporcione el rol. 
  
     ![Defina el grupo de servidores front-end.](../../media/c1447557-261e-4260-a362-ab8d19070eb9.png)
  
3. Escriba los nombres de dominio completos (FQDN) de todos los equipos del grupo y, a continuación, haga clic en **Siguiente** , como se muestra en la ilustración.
    
     ![Defina los equipos del grupo.](../../media/1106b4f3-8745-485b-b495-f885a5dfefda.png)
  
4. Seleccione las características que se incluirán en esta topología y, a continuación, haga clic en **Siguiente** , como se muestra en la ilustración.
    
    > [!NOTE]
    > Skype Empresarial Server incluye muchas características avanzadas. Revise la documentación de planeamiento e implementación para cada característica específica que quiera usar. 
  
     ![Seleccione las características de la implementación.](../../media/77257588-d0e1-4517-a12a-869ffe009353.png)
  
5. En la página **Seleccionar roles de servidor asignados** , puede optar por intercalar el servidor de mediación en el servidor front-end, o bien puede optar por implementarlo como un servidor independiente.
    
    Si tiene previsto intercalar el servidor de mediación en el grupo de servidores front-end Enterprise Edition, asegúrese de que la casilla está activada. Los roles de servidor se implementarán en los servidores del grupo. Si tiene previsto implementar el servidor de mediación como un servidor independiente, desactive la casilla adecuada. Implementará el servidor de mediación en un paso de implementación independiente después de implementar completamente el servidor front-end. Para obtener más información sobre la planeación de una ubicación, consulte [Conceptos básicos de topología para Skype Empresarial Server](../../plan-your-deployment/topology-basics/topology-basics.md).
    
6. Mediante el uso de la página **Asociar roles de servidor con este grupo de servidores front-end** , puede definir y asociar roles de servidor con el grupo de servidores front-end. Los tres roles disponibles son:
    
    **Habilitación de un grupo de Servidores perimetrales** Define y asocia un único servidor perimetral o un grupo de servidores perimetrales. Un servidor perimetral facilita la comunicación y la colaboración entre los usuarios de la organización y las personas ajenas a la organización, incluidos los usuarios federados.
    
    Hay dos escenarios posibles que puede usar para implementar y asociar los roles de servidor.
    
    Para el escenario uno, se define una nueva topología para una nueva instalación. Puede abordar la instalación de una de las dos maneras siguientes:
    
   - Deje la casilla desactivada y defina la topología. Después de publicar, configurar y probar los roles de servidor front-end y back-end, puede volver a ejecutar el Generador de topologías para agregar los servidores de roles a la topología. Con esta estrategia, puede probar el grupo de servidores front-end y el servidor que ejecuta SQL Server sin complicaciones adicionales de roles adicionales. Una vez completadas las pruebas iniciales, puede volver a ejecutar el Generador de topologías para seleccionar los roles que necesita implementar.
    
   - Seleccione los roles que necesita instalar y, a continuación, configure le hardware para hospedar los roles seleccionados.
    
     En el escenario dos, tiene una implementación existente y la infraestructura está lista para nuevos roles, o bien debe asociar los roles existentes a un nuevo servidor front-end.
    
   - En este caso, seleccionará los roles que piensa implementar o asociar con el nuevo servidor front-end. En cualquier caso, continuará con la definición de los roles, la configuración de cualquier hardware necesario y procederá con la instalación.
    
7. A continuación, definirá el almacén de SQL Server que se usará con la topología. En este ejemplo, usamos la instancia predeterminada. Para obtener más información sobre SQL Server características, como alta disponibilidad, consulte [Planeamiento de la alta disponibilidad y recuperación ante desastres en Skype Empresarial Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
    
   - Para usar el almacén de SQL Server existente que ya se ha definido en la topología, seleccione **Usar un almacén de SQL definido previamente**.
    
   - Para definir una nueva instancia de SQL Server para almacenar información del grupo, haga clic en **Nuevoy**, a continuación, especifique el **FQDN de SQL Server** en el cuadro de diálogo **Definir nuevo almacén de SQL**.
    
   - Para especificar el nombre de una instancia de SQL Server, seleccione **Instancia con nombre** y, a continuación, especifique el nombre de la instancia.
    
   - Para usar la instancia predeterminada, haga clic en **Instancia predeterminada**.
    
   - Para usar SQL creación de reflejo, seleccione **Habilitar SQL creación de reflejo** y seleccione una instancia existente o cree una nueva instancia.

     > [!NOTE]
     > la creación de reflejo de SQL está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. Los grupos de disponibilidad AlwaysOn, las instancias de clúster de conmutación por error alwayson (FCI) y los métodos de agrupación en clústeres de conmutación por error de SQL se prefieren con Skype Empresarial Server 2019.
    
     En este ejemplo, se escribe el **FQDN de SQL Server** y se configura cualquier configuración de alta disponibilidad pertinente y, a continuación, se hace clic en **Aceptar**, como se muestra en la ilustración.
    
     ![Cree un almacén de SQL Server.](../../media/12822cf9-8608-43c0-94ce-2ca8b3a0ffd5.png)
  
8. Decida si desea habilitar la creación de reflejo de SQL Server almacén o SQL Server testigo de creación de reflejo y, a continuación, haga clic en **Siguiente**.
    
9. Defina el recurso compartido de archivos que desea usar.
    
   - Para usar un uso compartido de archivos ya definido en la topología, seleccione **Usar un uso compartido de archivos ya definido**.
    
   - Para definir un nuevo recurso compartido de archivos, seleccione **Definir un nuevo recurso compartido de archivos**, en el cuadro **FQDN de servidor de archivos**, escriba el FQDN del servidor de archivos existente donde se ubicará el recurso compartido de archivos y, a continuación, escriba un nombre para el recurso compartido de archivos en el cuadro **Recurso compartido de archivos**.
    
     En este ejemplo, haremos clic en **Definir un nuevo almacén de archivos**, escribiremos el **FQDN del servidor de archivos** y el **recurso compartido de archivos** y, a continuación, haremos clic en **Siguiente**.
    
     > [!NOTE]
     > El recurso compartido de archivos para Skype Empresarial Server se puede colocar, pero no se recomienda por motivos de rendimiento. Tenga en cuenta que en este ejemplo, el recurso compartido de archivos se ha ubicado en un único servidor dedicado que actuará como recurso compartido de archivos. Sin embargo, se recomiendan otros sistemas de recursos compartidos de archivos más sólidos, como DFS mediante Windows Server 2012 R2. Para obtener más información sobre los sistemas de recursos compartidos de archivos admitidos, consulte [Requisitos para el entorno de Skype Empresarial](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md). Para obtener más información sobre cómo crear el recurso compartido de archivos, consulte [Creación de un recurso compartido de archivos en Skype Empresarial Server](create-a-file-share.md). Puede definir el uso compartido de archivos sin que este se haya creado. Tendrá que crear el uso compartido de archivos en la ubicación que defina antes de publicar la topología. 
  
10. En la página Especificar la dirección URL de los servicios web, debe decidir si necesita invalidar la dirección URL base del grupo de servicios web interno. El motivo de esta invalidación tiene que ver con el equilibrio de carga. El tráfico SIP básico se puede equilibrar mediante el equilibrio de carga de DNS simple. Sin embargo, el tráfico de red de servicios web HTTP/S debe usar una solución de equilibrio de carga de hardware o software compatible. Para ver los equilibradores de carga admitidos, consulte [Infraestructura para Skype Empresarial](../../../SfbPartnerCertification/certification/infra-gateways.md). En este ejemplo, usamos el equilibrio de carga DNS para el tráfico SIP y una solución de equilibrio de carga de software compatible. Dado que dividimos el tráfico de esta manera, es necesario invalidar el FQDN interno del grupo de servicios web. Como alternativa, si tuyéramos un equilibrador de carga de primera línea y enviábamos todo el tráfico a través de él en lugar de usar el equilibrio de carga DNS para el tráfico SIP, no necesitaríamos invalidar la dirección URL de servicios web. 
    
    En la sección DNS de este tema, creamos un registro A para `webint.contoso.local`. Esta es la dirección URL que se usa para el tráfico HTTP/S de los servicios web y debe pasar por el equilibrador de carga de software compatible que hemos configurado. Por lo tanto, en este ejemplo, invalidamos la dirección URL para que Skype Empresarial Server sepa que todo el tráfico HTTP/S debe ir a `webint.contoso.local` en lugar de `pool.contoso.local`, como se muestra en la ilustración. Para más información sobre el equilibrio de carga, consulte [Requisitos de equilibrio de carga para Skype Empresarial](../../plan-your-deployment/network-requirements/load-balancing.md).
    
    > [!IMPORTANT]
    > La dirección URL base es la identidad de servicios web de la dirección URL, menos https://. Por ejemplo, si la dirección URL completa de los servicios web del grupo es `https://webint.contoso.local`, la dirección URL base es `webint.contoso.local`. 
  
    - Si va a configurar el equilibrio de carga de DNS, como se muestra en este ejemplo, active la casilla **Invalidar FQDN del grupo de servicios web internos** y escriba la dirección URL base interna (que debe ser diferente del FQDN del grupo) en **Dirección URL base interna**. 
    
    > [!CAUTION]
    > Si decide invalidar los servicios web internos con un FQDN autodefinida, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores. **Use solo caracteres estándar** (incluidos A-Z, a-z, 0-9 y guiones) al definir direcciones URL o nombres de dominio completos. No use caracteres Unicode ni de subrayado. Los caracteres no estándar de una dirección URL o FQDN a menudo no son compatibles con dns externo y entidades de certificación públicas (CA) (es decir, cuando la dirección URL o el FQDN deben asignarse al nombre del firmante o al nombre alternativo del firmante en el certificado).
  
    - Opcionalmente, escriba la dirección URL base externa en **Dirección URL base externa**. Escribiría la dirección URL base externa para diferenciarla del nombre de dominio interno. Por ejemplo, el dominio interno es `contoso.local`, pero el nombre de dominio externo es `contoso.com`. Definiría la dirección URL mediante el nombre de `contoso.com` dominio, ya que debe poder resolverse a partir de DNS público. También es importante en el caso de un proxy inverso. El nombre de dominio de la dirección URL base externa será el mismo que el nombre de dominio del FQDN del servidor proxy inverso. El acceso HTTP al grupo de servidores front-end es necesario para la mensajería instantánea y la presencia en clientes móviles.
    
      ![Invalide los servicios web.](../../media/8f95313c-2df4-4885-adc5-9fc9ea775406.png)
  
11. Si seleccionó **Conferencia** en la página **Seleccionar características**, se le pedirá que seleccione un servidor Office Web Apps. Haga clic en **Nuevo** para iniciar el cuadro de diálogo.
    
12. En el cuadro de diálogo **Definir nuevo servidor Office Web Apps**, escriba el FQDN del servidor de Office Web Apps en el cuadro **FQDN del servidor de Office Web Apps**; al hacerlo, el Office Web Apps  La dirección URL de detección del servidor se debe escribir automáticamente en el cuadro **Office Web Apps Dirección URL de detección del servidor**.
    
    Si el servidor de Office Web Apps está instalado de forma local y en la misma zona de red que Skype Empresarial Server, no seleccione la opción **Office Web Apps Server se implementa en una red externa (es decir, perímetro/Internet).**
    
    Si el servidor de Office Web Apps se implementa fuera del firewall interno, seleccione la opción **Office Web Apps Server se implementa en una red externa (es decir, perímetro/Internet).**
    
13. Haga clic en **Finalizar** para completar la configuración. Si ha definido otros servidores de roles en la página **Asociar roles de servidor con este grupo de servidores front-end** , se abrirán páginas independientes del Asistente para la configuración de roles, donde podrá configurar los roles de servidor. En este ejemplo solo elegimos conferencias.
    
### <a name="configure-simple-urls"></a>Configuración de direcciones URL sencillas

1. En el Generador de topologías, haga clic con el botón derecho en el **Skype Empresarial Server** nodo superior y, a continuación, haga clic en **Editar propiedades**, como se muestra en la ilustración.
    
     ![Haga clic con el botón derecho en Skype Empresarial Server y seleccione Editar propiedades.](../../media/692c18dd-8e99-4239-ae7b-5e855d866afa.png)
  
2. En el panel **Direcciones URL simples**, seleccione **Teléfono direcciones URL de acceso:** (acceso telefónico local) o **Direcciones URL de reunión:** (Reunión) para editar y, a continuación, haga clic en **Editar dirección URL**.
    
3. Actualice la dirección URL al valor deseado y haga clic en **Aceptar** para guardar la dirección URL modificada. Debe configurar la dirección URL simple mediante el dominio SIP externo para que los usuarios externos puedan unirse a reuniones, por ejemplo, `contoso.com`, que es externo, en lugar de `contoso.local`, que es un dominio interno. Por lo tanto, el dominio SIP debe ser capaz de resolverse mediante DNS externo.
    
4. Edite la dirección URL de reunión realizando los mismos pasos, si es necesario.
    
### <a name="to-define-the-optional-admin-simple-url"></a>Para definir la dirección URL sencilla de administración opcional

1. En el Generador de topologías, haga clic con el botón derecho en el nodo **Skype Empresarial Server** y, a continuación, haga clic en **Editar propiedades**.
    
2. En el cuadro **Dirección URL de acceso administrativo**, escriba la dirección URL simple que desea para el acceso administrativo a Skype Empresarial Server Panel de control y, a continuación, haga clic en **Aceptar**.
    
    > [!TIP]
    > Recomendamos usar la dirección URL más simple posible para la dirección URL de administración. La opción más sencilla es https://admin. _\<domain\>_ La dirección URL de Administración puede ser un dominio interno o externo, por ejemplo, `contoso.local` o , siempre que `contoso.com`cualquiera de los registros se pueda resolver en DNS interno. 
  
    > [!IMPORTANT]
    > Si cambia una dirección URL sencilla tras la implementación inicial, deberá conocer qué cambios afectan a los certificados y los registros de su sistema de nombres de dominio (DNS) para direcciones de URL sencillas. Si el cambio afecta a la base de una dirección URL simple, también debe cambiar los registros y certificados DNS. Por ejemplo, cambiar de `https://sfb.contoso.com/Meet` a `https://meet.contoso.com` cambia la dirección URL base de sfb.`contoso.com` a `meet.contoso.com`, por lo que tendría que cambiar los registros y certificados DNS para hacer referencia a `meet.contoso.com`. Si ha cambiado la dirección URL simple de `https://sfb.contoso.com/Meet` a `https://sfb.contoso.com/Meetings`, la dirección URL base de `sfb.contoso.com` permanece igual, por lo que no se necesita ningún cambio de DNS o certificado. Sin embargo, siempre que cambie un nombre de dirección URL simple, debe ejecutar el cmdlet **Enable-CsComputer** en cada servidor director y front-end para registrar el cambio.
  
### <a name="publish-and-verify-the-topology"></a>Publicación y comprobación de la topología

1. Compruebe que todas las URL sencillas están configuradas correctamente.
    
2. Confirme que el servidor basado en SQL Server está en línea y disponible para el equipo donde está instalado el Generador de topologías, incluidas las reglas de firewall necesarias.
    
3. Confirme que el recurso compartido de archivos está disponible y que se definen los permisos adecuados.
    
4. Confirme que se han definido en la topología los roles de servidor correctos que cumplen los requisitos de la implementación.
    
5. Compruebe que los servidores existen en Servicios de dominio de Active Directory (AD DS). Esto sucede automáticamente cuando se unen los servidores al dominio.
    
    Una vez que haya verificado la topología y comprobado que no existen errores de validación, estará listo para publicar la topología. Si hay errores de validación, debe corregirlos antes de poder publicar la topología.
    
6. Haga clic con el botón derecho en el nodo **Skype Empresarial Server** y, a continuación, haga clic en **Publicar topología**.
    
7. En la página **Publicar topología**, haga clic en **Siguiente**.
    
8. En la página **Seleccionar servidor de administración central** , seleccione un grupo de servidores front-end, como se muestra en la ilustración.
    
    > [!NOTE]
    > Puede hacer clic en **Avanzadas** para configurar las ubicaciones de los archivos de base de datos.
  
     ![Seleccione Servidor del Almacén de administración central.](../../media/764478b5-8480-42c5-854f-649bb121cd94.png)
  
9. En la página **Seleccionar bases de datos** , seleccione las bases de datos que desea publicar.
    
    > [!NOTE]
    > Si no tiene los derechos adecuados para crear las bases de datos, puede desactivar las casillas situadas junto a esas bases de datos y alguien con los derechos adecuados puede crear las bases de datos más adelante. Para obtener más información sobre los requisitos, consulte [Requisitos del servidor para Skype Empresarial Server](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md). 
  
10. Opcionalmente, haga clic en **Avanzadas**. Si usa opciones avanzadas de selección de ubicación de archivos de datos SQL Server, puede seleccionar entre las siguientes opciones: 
    
    - **Determinación automática de la ubicación del archivo de base** de datos: esta opción determina el mejor rendimiento operativo en función de la configuración del disco en el servidor basado en SQL Server mediante la distribución de los archivos de registro y datos a la mejor ubicación.
    
    - **Usar SQL Server valores predeterminados de instancia**: esta opción coloca los archivos de registro y datos en el servidor basado en SQL Server mediante la configuración de la instancia. No usa la funcionalidad operativa del servidor basado en SQL Server para determinar las ubicaciones óptimas de registros y datos. El administrador de SQL Server suele mover los archivos de datos y de registro a ubicaciones que sean adecuadas para los procedimientos de administración de la organización y del servidor basado en SQL Server.
    
    Haga clic en **Aceptar** y después en **Siguiente**. 
    
11. Opcionalmente, haga clic en **Opciones avanzadas**. Si usa opciones avanzadas de selección de ubicación de archivos de datos SQL Server, puede seleccionar entre las siguientes opciones: 
    
    - **Determinación automática de la ubicación del archivo de base** de datos: esta opción determina el mejor rendimiento operativo en función de la configuración del disco en el servidor basado en SQL Server mediante la distribución de los archivos de registro y datos a la mejor ubicación.
    
    - **Usar SQL Server valores predeterminados de instancia**: esta opción coloca los archivos de registro y datos en el servidor basado en SQL Server mediante la configuración de la instancia. No usa la funcionalidad operativa del servidor basado en SQL Server para determinar las ubicaciones óptimas de registros y datos. El administrador de SQL Server suele mover los archivos de datos y de registro a ubicaciones que sean adecuadas para los procedimientos de administración de la organización y del servidor basado en SQL Server.
    
    Haga clic en **Aceptar**.
    
12. Haga clic en **Siguiente** para completar el proceso de publicación.
    
    > [!NOTE]
    > Un error común en este paso es que no se pueden crear las bases de datos de SQL Server. Cuando el proceso no se puede completar, se proporciona un error, como se muestra en la ilustración. La causa más probable es que el usuario que intenta crear la base de datos no tenga los permisos adecuados o que no se pueda ponerse en contacto con el sistema SQL Server debido a un firewall u otro problema de red. 
  
     ![Error al crear el almacén de administración central.](../../media/558bd2e4-2721-422d-9986-df86f642e6a1.png)
  
13. Cuando se complete el proceso de publicación, se le mostrará un vínculo para abrir una lista de los pasos siguientes. Haga clic en **Haga clic aquí para abrir la lista de tareas pendientes** para ver los pasos siguientes y, a continuación, haga clic en **Finalizar**. 
    
    El mensaje "Completado con advertencias" para la creación de la base de datos no significa que se haya producido un error. El proceso de instalación tiene que cambiar la configuración de SQL Server para que Skype Empresarial Server funcione correctamente. Cuando se cambia una configuración en SQL Server, se registra como una advertencia para que SQL Server administradores puedan comprender exactamente cuál es el proceso de instalación completado. Si recibe una advertencia, puede seleccionar el registro y, a continuación, hacer clic en **Ver registros** para ver los detalles de la advertencia.
    
    Cuando la topología se haya publicado correctamente, puede empezar a instalar una réplica local del almacén de administración central en cada servidor que ejecute Skype Empresarial Server en la topología. Se recomienda empezar por el primer grupo de servidores front-end. 
