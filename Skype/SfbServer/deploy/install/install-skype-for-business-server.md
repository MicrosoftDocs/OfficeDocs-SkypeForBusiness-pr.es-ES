---
title: Instalar Skype Empresarial Server en los servidores de la topología
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Resumen: Obtenga información sobre cómo instalar el Skype para los componentes del sistema de Business Server en cada servidor de la topología. Descargue una versión de prueba gratuita de Skype para Business Server desde el Evaluation de Microsoft center en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 41fbe8db0d279d9cace577e1977c093fd794693b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20994708"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Instalar Skype Empresarial Server en los servidores de la topología
 
**Resumen:** Obtenga información sobre cómo instalar el Skype para los componentes del sistema de Business Server en cada servidor de la topología. Descargue una versión de prueba gratuita de Skype para Business Server desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Una vez que la topología se carga en el almacén de Administración Central y Active Directory sabe en qué servidores llevará a cabo las funciones, debe instalar el Skype para sistema Business Server en cada uno de los servidores de la topología. Se pueden realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5 tal como se indica en el diagrama. Instalar el Skype para sistema Business Server es el paso 7 de 8.
  
![Diagrama de información general.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Instalar Skype para sistema Business Server

Una vez haya publicado una topología, puede instalar el Skype para los componentes de Business Server en cada servidor de la topología. Esta sección le guiará a través de la instalación de Skype para Business Server y la configuración de las funciones de servidor para el grupo de servidores Front-End y los roles de servidor que se combinan con los servidores Front-End. Para instalar y configurar las funciones de servidor, ejecute el Skype para el Asistente para la implementación de Business Server en cada equipo en el que va a instalar una función de servidor. Utilice el Asistente para la implementación para completar los cuatro pasos de este proceso, incluida la instalación del almacén de configuración local, la instalación de los servidores front-end, la configuración de los certificados y la puesta en marcha de los servicios.
  
> [!IMPORTANT]
> Debe usar el generador de topología para finalizar y publicar la topología antes de instalar Skype para Business Server en servidores. 
  
> [!NOTE]
> Debe completarse este procedimiento para todos los servidores de la topología. 
  
> [!CAUTION]
> Después de instalar Skype para Business Server en un servidor Front-End, la primera vez que inicie los servicios, debe asegurarse de que se está ejecutando el servicio de Firewall de Windows en el servidor. 
  
> [!CAUTION]
> Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que sea un administrador local y miembro del grupo RTCUniversalServerAdmins. 
  
> [!NOTE]
> Si no ha ejecutado Skype para el programa de instalación de Business Server en este servidor antes, se le pedirá para una unidad y la ruta de acceso para la instalación. Esto ofrece la posibilidad de instalarlo en una unidad diferente a la del sistema, en caso de que su organización así lo precise o si tiene problemas de espacio. Puede cambiar la ruta de acceso de ubicación de instalación para el Skype para los archivos del servidor de negocio en el cuadro de diálogo **el programa de instalación** para una nueva unidad disponible. Si instala los archivos del programa de instalación para esta ruta de acceso, incluidos OCSCore.msi, el resto de la Skype para los archivos de Business Server va a implementar existe también.
  
> [!IMPORTANT]
> Antes de comenzar la instalación, asegúrese de que el servidor de Windows está actualizado mediante el uso de Windows Update. 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Instalar Skype para sistema Business Server

1. Inserte el Skype para los medios de instalación de Business Server. Si la configuración no empieza automáticamente, haga doble clic en **Configuración**.
    
2. La ejecución del soporte de instalación requiere Microsoft Visual C++. Aparecerá un cuadro de diálogo preguntándole si quiere instalarlo. Haga clic en **Sí.**
    
3. Revise cuidadosamente el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Aceptar**. 
    
4. El programa de instalación inteligente es una característica de Skype para Business Server donde puede conectarse a Internet para comprobar las actualizaciones de Microsoft Update (MU) durante el proceso de instalación, tal como se muestra en la ilustración. Esto proporciona una experiencia más gratificante, asegurándose de que tiene las actualizaciones más recientes para el producto. Haga clic en **Instalar** para iniciar la instalación.
    
    > [!NOTE]
    > Muchas organizaciones tienen Windows Server Update Services (WSUS) implementado en sus entornos corporativos. WSUS permite a los administradores administrar por completo la distribución de actualizaciones que se publiquen a través de Microsoft Update en su red. Como parte de la versión de actualización acumulativa 1 Skype para Business Server introdujo la compatibilidad con el programa de instalación inteligente para que funcione con WSUS. Los clientes con WSUS que va a implementar Skype para Business Server por primera vez o actualizar desde el entorno de Lync Server 2013 mediante la característica In-Place Upgrade tendrán inteligentes del programa de instalación la obtención de actualizaciones de Skype para Windows de WSUS en contraposición a la obtención de actualizaciones de MU. Los clientes que deseen usar la configuración inteligente tienen que ejecutar el SmartSetupWithWSUS.psq en todos los equipos antes de ejecutar Setup.exe. 
  
     ![Captura de pantalla de configuración inteligente](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. En la página Asistente para la implementación, haga clic en **instalar o actualización de Skype para Business Server System**.
    
6. Realizar los procedimientos en los siguientes procedimientos, cuando haya finalizado, haga clic en **Salir** para cerrar el Asistente para la implementación. Repita los procedimientos para cada servidor front-end del grupo.
    
### <a name="step-1-install-local-configuration-store"></a>Paso 1: Instalar almacén de configuración local

1. Revise los requisitos previos y haga clic en **Ejecutar**, junto a **Paso 1: Instalar almacén de configuración local**.
    
    > [!NOTE]
    > El almacén de configuración local es una copia de solo lectura del Almacén de administración central. En una implementación Standard Edition, el Almacén de administración central se crea con una copia local de SQL Server Express Edition en el servidor front-end al ejecutarse el procedimiento Preparar el primer servidor de Standard Edition. En una implementación de Enterprise Edition, el Almacén de administración central se crea cuando se publica una topología que incluya un grupo front-end Enterprise Edition. 
  
2. En la página **Instalar almacén de configuración local**, asegúrese de que la opción **Recuperar directamente del Almacén de administración central** esté seleccionada y luego haga clic en **Siguiente**.
    
    SQL Server Express Edition, que es necesario para el almacén de configuración local, se instala en el servidor local.
    
3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Paso 2: Instalar o desinstalar Skype para los componentes de Business Server

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto a **paso 2: el programa de instalación o quitar Skype para los componentes de servidor empresariales**.
    
2. En la página **Establecer Skype para los componentes de servidor empresariales** , haga clic en **siguiente** para configurar los componentes según se define en la topología publicada.
    
3. La página **Ejecución de comandos** muestra un resumen de los comandos, así como también información sobre la instalación a medida que se realiza. Cuando está listo, puede usar la lista para seleccionar un registro para ver y, a continuación, haga clic en **Ver registro**.
    
4. Cuando se realiza Skype para la instalación de los componentes de Business Server y que haya revisado los registros según sea necesario, haga clic en **Finalizar** para completar este paso en la instalación.
    
    > [!NOTE]
    > Reinicie el servidor si se le pide (puede ser el caso si fue necesario instalar la Experiencia de escritorio de Windows). Cuando el equipo está de vuelta y en funcionamiento, debe ejecutar este (paso 2: el programa de instalación o quitar Skype para los componentes de servidor empresariales) nuevo procedimiento. 
  
    > [!NOTE]
    > Si el instalador detecta que no se cumple algún requisito previo, se lo comunicará por medio de un mensaje ("Requisito previo no satisfecho") como el de la figura. Cumplir el requisito previo necesario y, a continuación, iniciar este (paso 2: el programa de instalación o quitar Skype para los componentes de servidor empresariales) nuevo procedimiento. 
  
     ![Prerrequisito necesario.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Compruebe que los dos primeros pasos se han completado del modo esperado. Confirme que hay una marca de verificación verde con la palabra **Completado**, como se muestra en la figura.
    
     ![Primeros dos pasos de la instalación de componentes completos.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Ejecute **Windows Update** para comprobar si hay actualizaciones después de instalar el Skype para los componentes de servidor empresariales.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Paso 3: Solicitar, instalar o asignar certificados

1. Revise los requisitos previos y haga clic en **Ejecutar**, junto a **Paso 3: Solicitar, instalar o asignar certificados**.
    
    > [!NOTE]
    > Skype para Business Server incluye compatibilidad con el conjunto de aplicaciones SHA-2 (SHA-2 usa implícita longitudes de 224, 256, 384 o 512 bits) de síntesis hash y algoritmos para las conexiones de los clientes que ejecutan el 10 de Windows, Windows 8, Windows 7, Windows Server 2012 R2, Windows de firma Server 2012, o sistemas operativos Windows Server 2008 R2. Para permitir el acceso externo mediante el conjunto de aplicaciones SHA-2, el certificado externo lo emite una CA pública que también puede emitir un certificado con las mismas longitudes de bits de síntesis. 
  
    > [!IMPORTANT]
    > La selección de la síntesis de hash y el algoritmo de firma depende de los clientes y de los servidores que usarán el certificado y de otros equipos y dispositivos con los que los clientes y servidores se comunicarán, quienes también deben saber cómo usar los algoritmos del certificado. Para obtener información sobre qué implícita longitudes son compatibles con el sistema operativo y algunas aplicaciones de cliente, consulte el [blog de PKI de Windows: SHA2 y Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Cada servidor Standard Edition o front-end necesita hasta cuatro certificados: el certificado oAuthTokenIssuer, un certificado predeterminado, un certificado web interno y un certificado web externo. Pero, es posible solicitar y asignar un solo certificado predeterminado con las entradas de nombre alternativo de sujeto apropiadas, así como el certificado oAuthTokenIssuer. Para obtener información detallada acerca de los requisitos de certificado, vea [requisitos de entorno para Skype para Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos de servidor para Skype para Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > El siguiente procedimiento describe cómo configurar certificados de una entidad de certificación interna basada en Servicios de certificados de Active Directory. 
  
2. En la página **Asistente para certificados**, haga clic en **Solicitar**.
    
3. En la página **Solicitud de certificado**, rellene los datos necesarios, incluida la selección de dominio SIP, y haga clic en **Siguiente**.
    
4. En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente a una entidad de certificación en línea** haciendo clic en **Siguiente**. La CA interna con inscripción en línea automática debe estar disponible si selecciona esta opción. Si elige la opción para retrasar la solicitud, se le pedirá un nombre y una ubicación para guardar el archivo de solicitud de certificado. La solicitud de certificado debe ser presentada y procesada por una CA de su organización o bien por una CA pública. Después, tendrá que importar la respuesta de certificado y asignarla al rol de certificado apropiado.
    
5. En la página **Elija una entidad de certificación (CA)** , seleccione la opción de **Seleccionar una entidad de certificación de la lista detectada en su entorno** y, a continuación, seleccione un conocidos (mediante el registro en los servicios de dominio de Active Directory) entidad emisora de certificados de la lista. O bien, seleccione la opción **Especificar otra entidad de certificación** escriba el nombre de otra CA en el cuadro y haga clic en **Siguiente**.
    
6. En la página **Cuenta de la entidad de certificación**, se solicitan sus credenciales para solicitar y procesar la solicitud de certificado en la CA. Es necesario que haya determinado si es necesario un nombre de usuario y una contraseña para solicitar un certificado por adelantado. Su administrador de CA tendrá la información necesaria y es posible que tenga que ayudarle en este paso. Si tiene que especificar credenciales alternativas, active la casilla, escriba un nombre de usuario y una contraseña en los cuadros de texto y haga clic en **Siguiente**.
    
7. En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente** para usar la plantilla de servidor web predeterminada.
    
    > [!NOTE]
    > Si su organización ha creado una plantilla para usar como alternativa a la plantilla de la CA de servidor web predeterminada, seleccione la casilla y escriba el nombre de la plantilla alternativa. Necesitará el nombre de la plantilla definido por el administrador de CA. 
  
8. En la página **nombre y configuración de seguridad** , especifique un **Nombre descriptivo**. Mediante el uso de un nombre descriptivo, puede identificar rápidamente el certificado y el propósito. Si deja en blanco, se generará automáticamente un nombre. Establecer la **longitud en bits** de la clave o acepte el valor predeterminado de 2048 bits. Seleccione el **marcar la clave privada del certificado como exportable** si determina que necesita el certificado y la clave privada va a mover o copiar en otros sistemas y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Skype para Business Server tiene requisitos mínimos para una clave privada exportable. Uno de estos sitios se encuentra en los servidores perimetrales en un grupo de servidores, donde el servicio de autenticación relé multimedia usa copias del certificado, en lugar de certificados individuales para cada instancia en el grupo de servidores. 
  
9. En la página **Información de la organización**, si lo desea, proporcione información de la organización y después haga clic en **Siguiente**.
    
10. En la página **Información geográfica**, si lo desea, escriba información geográfica y después haga clic en **Siguiente**.
    
11. En la página **Nombre del sujeto/Nombres alternativos del juego**, revise los nombres alternativos del sujeto que se van a agregar y haga clic en **Siguiente**.
    
12. En la página **Configuración del dominio SIP**, active la casilla **Dominio SIP** y haga clic en **Siguiente**.
    
13. En la página **Configurar nombres alternativos de sujeto adicionales**, agregue los nombres alternativos de sujeto adicionales que desee, incluido cualquiera que piense que puede ser necesario para dominios SIP adicionales en el futuro, y haga clic en **Siguiente**.
    
14. En la página **Resumen de la solicitud de certificados**, revise la información del resumen. Si la información es correcta, haga clic en **Siguiente**. Si necesita corregir o modificar una configuración, haga clic en **Atrás** para ir a la página pertinente y realizar la corrección o modificación.
    
15. En la página **Ejecución de comandos**, haga clic en **Siguiente**.
    
16. En la página **Estado de la solicitud de certificado en línea**, revise la información devuelta. Tenga en cuenta que el certificado se emitió e instaló en el almacén de certificados local. Si se crea un informe tal y como se ha emitido e instalado, pero no es válido, asegúrese de que se ha instalado el certificado de entidad de certificación raíz en el almacén del servidor CA raíz de confianza. Consulte la documentación de la CA para más información sobre cómo recuperar un certificado de CA raíz de confianza. Si necesita ver el certificado recuperado, haga clic en **Ver detalles del certificado**. De forma predeterminada, se selecciona la casilla de verificación para **asignar el certificado a Skype para usos de certificados de servidor empresarial** . Si desea asignar el certificado manualmente, desactive la casilla y haga clic en **Finalizar**.
    
17. Si desactiva la casilla de verificación para **asignar el certificado a Skype para usos de certificados de servidor de negocio** en la página anterior, aparecerá la página **Asignación de certificados** . Haga clic en **Siguiente**.
    
18. En la página **Almacén de certificados**, seleccione el certificado solicitado. Si desea ver el certificado, haga clic en **Ver detalles del certificado** y en **Siguiente** para continuar.
    
    > [!NOTE]
    > Si en la página **Estado de la solicitud de certificado en línea** se ha indicado algún problema con el certificado (como que el certificado no es válido), ver el certificado real puede resultarle de ayuda para resolver el problema. Dos problemas específicos que pueden hacer que un certificado no sea válido son que falte el certificado de la CA raíz de confianza mencionado anteriormente o que falte una clave privada asociada con el certificado. Consulte la documentación de la CA para resolver estos dos problemas.
  
19. En la página **Resumen de asignación de certificados**, revise la información proporcionada para garantizar que este sea el certificado que debe asignarse y haga clic en **Siguiente**.
    
20. En la página **Ejecución de comandos**, revise el resultado del comando. Haga clic en **Ver registro** si desea revisar el proceso de asignación o si se ha emitido algún error o advertencia. Cuando termine, haga clic en **Finalizar**.
    
21. En la página **Asistente para certificados**, confirme que todos los servicios tienen una marca de verificación verde, lo que indica que todos ellos tienen asignado un certificado (OAuthTokenIssuer incluido), como se muestra en la figura. Luego, haga clic en **Cerrar**.
    
     ![Certificados instalados y asignados correctamente.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Si está realizando la instalación en un entorno de laboratorio y acaba de configurar la entidad de certificación con Servicios de certificados de Active Directory, necesitará reiniciar tanto el servidor donde se ejecutan los Servicios de certificados como el servidor front-end para que la asignación de certificados se efectúe correctamente. 
  
    > [!TIP]
    >  Para obtener más información acerca de los certificados en los servicios de certificados de Active Directory, vea [Servicios de certificados de Active Directory](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx). 
  
### <a name="step-4-start-services"></a>Paso 4: Iniciar los servicios

1. Revise los requisitos del **Paso 4: Iniciar servicios**.
    
2. Si se trata de un grupo de servidores front-end Enterprise Edition con al menos tres servidores, se usa Windows Fabric, y necesitará usar el cmdlet **Start-CsPool**. Si se utiliza un único servidor, que siempre es el caso de Standard Edition, muse use el cmdlet **Start-CsWindowsService** . En este ejemplo se usa con tres servidores Front-End del grupo de servidores Enterprise Edition, abra el **Skype para Business Server Management Shell** y ejecute el cmdlet **Start-CsPool** tal como se muestra en la ilustración. Para el resto de los roles (incluido el servidor Standard Edition), use **Start-CsWindowsService**. Para implementar roles que no sean el rol de servidor front-end, consulte la documentación de los roles en cuestión.
    
     ![Inicia los servicios de Skype Empresarial.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. En la página **Ejecución de comandos**, una vez que todos los servicios se hayan iniciado correctamente, haga clic en **Finalizar**.
    
    > [!IMPORTANT]
    > El comando para iniciar los servicios en el servidor es un método de mejor esfuerzo para informar de que los servicios, efectivamente, se han iniciado. Es posible que no refleje el estado actual del servicio. Recomendamos llevar a cabo el paso **Estado del servicio (opcional)** para abrir Microsoft Management Console (MMC) y confirmar que los servicios se han iniciado correctamente, como se indica en la figura. Si cualquier Skype para servicio Business Server no se ha iniciado, puede secundario de ese servicio en MMC y, a continuación, haga clic en **Iniciar**. 
  
     ![Ha comenzado la verificación de servicios.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

