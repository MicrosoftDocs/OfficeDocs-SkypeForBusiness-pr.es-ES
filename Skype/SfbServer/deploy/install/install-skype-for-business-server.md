---
title: Instalar Skype empresarial Server en los servidores de la topología
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Resumen: Obtenga información sobre cómo instalar los componentes del sistema de Skype empresarial Server en cada servidor de la topología. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serveren:.'
ms.openlocfilehash: 0fe1c7b6088732932457d25c68a8fd6476a1bfbd
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018251"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Instalar Skype empresarial Server en los servidores de la topología
 
**Resumen:** Obtenga información sobre cómo instalar los componentes del sistema de Skype empresarial Server en cada servidor de la topología. Descargue una versión de prueba gratuita de Skype empresarial Server del [centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Una vez que se carga la topología en el almacén de administración central y Active Directory sabe qué servidores realizarán cada rol, debe instalar el sistema de Skype empresarial Server en cada uno de los servidores de la topología. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos 1 a 5, tal como se describe en el diagrama. La instalación de Skype empresarial Server System es el paso 7 de 8.
  
![Diagrama de información general.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Instalar el sistema de Skype empresarial Server

Una vez que haya publicado una topología, puede instalar los componentes de Skype empresarial Server en cada servidor de la topología. Esta sección le guiará a través de la instalación de Skype empresarial Server y la configuración de las funciones de servidor para el grupo de servidores front-end y los roles de servidor combinados con los servidores front-end. Para instalar y configurar roles de servidor, ejecute el Asistente para la implementación de Skype empresarial Server en cada equipo en el que vaya a instalar una función de servidor. Use el Asistente para la implementación para completar los cuatro pasos de implementación, incluida la instalación del almacén de configuración local, la instalación de los servidores front-end, la configuración de certificados y el inicio de los servicios.
  
> [!IMPORTANT]
> Debe usar el generador de topologías para completar y publicar la topología antes de poder instalar Skype empresarial Server en los servidores. 
  
> [!NOTE]
> Este procedimiento debe completarse para todos los servidores de la topología. 
  
> [!CAUTION]
> Después de instalar Skype empresarial Server en un servidor front-end, la primera vez que inicie los servicios, debe asegurarse de que el servicio Firewall de Windows se está ejecutando en el servidor. 
  
> [!CAUTION]
> Antes de seguir estos pasos, asegúrese de haber iniciado sesión en el servidor con una cuenta de usuario de dominio que sea un administrador local y un miembro del grupo RTCUniversalServerAdmins. 
  
> [!NOTE]
> Si aún no ha ejecutado el programa de instalación de Skype empresarial Server en este servidor, se le pedirá una unidad y una ruta de acceso para la instalación. Esto proporciona la capacidad de instalar en una unidad distinta de la unidad del sistema, si su organización la necesita, o si tiene problemas de espacio. Puede cambiar la ruta de acceso de la ubicación de instalación de los archivos de Skype empresarial Server en el cuadro de diálogo de **configuración** a una nueva unidad disponible. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Skype empresarial Server también se implementarán allí.
  
> [!IMPORTANT]
> Antes de comenzar con la instalación, asegúrese de que Windows Server está actualizado mediante Windows Update. 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Instalar el sistema de Skype empresarial Server

1. Inserte los medios de instalación de Skype empresarial Server. Si el programa de instalación no se inicia automáticamente, haga doble clic en **setup**.
    
2. El medio de instalación requiere que se ejecute Microsoft Visual C++. Aparecerá un cuadro de diálogo preguntándole si quiere instalarlo. Haga clic en **sí.**
    
3. Revise atentamente el contrato de licencia y, si está de acuerdo, seleccione Acepto **los términos del contrato de licencia**y haga clic en **Aceptar**. 
    
4. La configuración inteligente es una característica de Skype empresarial Server en la que puede conectarse a Internet para comprobar si hay actualizaciones de Microsoft Update (MU) durante el proceso de instalación, tal como se muestra en la figura. Esto proporciona una mejor experiencia asegurándose de que tiene las actualizaciones más recientes para el producto. Haga clic en **Instalar** para comenzar el proceso de instalación.
    
    > [!NOTE]
    > Muchas organizaciones tienen Windows Server Update Services (WSUS) implementado en sus entornos corporativos. WSUS permite a los administradores administrar completamente la distribución de actualizaciones que se publican a través de Microsoft Update para los equipos de la red. Como parte de la actualización acumulativa 1, Skype empresarial Server incorporó compatibilidad para la configuración inteligente para trabajar con WSUS. Los clientes con WSUS que estén implementando Skype empresarial Server por primera vez o que actualicen desde el entorno de Lync Server 2013 con la característica de actualización local, tendrán la configuración inteligente para la recuperación de actualizaciones de Skype empresarial desde WSUS en lugar de obtener actualizaciones de MU. Los clientes que quieran usar la instalación inteligente deben ejecutar el SmartSetupWithWSUS. PSQ en todas las máquinas antes de ejecutar SETUP. exe. 
  
     ![Captura de pantalla de configuración inteligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. En la página Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**.
    
6. Realice los procedimientos de los siguientes procedimientos, cuando haya terminado, haga clic en **salir** para cerrar el Asistente para la implementación. Repita los procedimientos para cada servidor front-end del grupo de servidores.
    
### <a name="step-1-install-local-configuration-store"></a>Paso 1: instalar el almacén de configuración local

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto al **paso 1: instalar almacén de configuración local**.
    
    > [!NOTE]
    > El almacén de configuración local es una copia de solo lectura del almacén de administración central. En una implementación de Standard Edition, el almacén de administración central se crea con una copia local de SQL Server Express Edition en el servidor front-end. Esto sucede cuando se ejecuta el procedimiento preparar el primer servidor Standard Edition. En una implementación de Enterprise Edition, el almacén de administración central se crea al publicar la topología que incluye un grupo de servidores front-end Enterprise Edition. 
  
2. En la página **instalar el almacén de configuración local** , asegúrese de que la opción **recuperar directamente del almacén de administración central** esté seleccionada y, a continuación, haga clic en **siguiente**.
    
    SQL Server Express Edition está instalado en el servidor local. SQL Server Express Edition es necesario para el almacén de configuración local.
    
3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Paso 2: configurar o quitar componentes de Skype empresarial Server

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto al **paso 2: configurar o quitar componentes de Skype empresarial Server**.
    
2. En la página **Configurar componentes de Skype empresarial Server** , haga clic en **siguiente** para configurar los componentes tal como se define en la topología publicada.
    
3. La página **ejecución de comandos** muestra un resumen de los comandos y la información de instalación a medida que se realiza la configuración. Cuando haya terminado, puede usar la lista para seleccionar un registro y, a continuación, hacer clic en **Ver registro**.
    
4. Cuando se haya completado la instalación de los componentes de Skype empresarial Server y haya revisado los registros según sea necesario, haga clic en **Finalizar** para completar este paso en la instalación.
    
    > [!NOTE]
    > Si se le pide, reinicie el servidor (lo que puede ocurrir si es necesario instalar la experiencia de escritorio de Windows). Cuando el equipo vuelva a estar en funcionamiento, deberá ejecutar este procedimiento (paso 2: instalar o quitar componentes de Skype empresarial Server) de nuevo. 
  
    > [!NOTE]
    > Si el instalador encuentra algún requisito previo que no se ha satisfecho, recibirá una notificación con el mensaje "prerrequisito no satisfecho", tal como se muestra en la figura. Cumpla el requisito previo necesario y, a continuación, inicie este procedimiento (paso 2: instalar o quitar componentes de Skype empresarial Server) de nuevo. 
  
     ![Requisitos previos necesarios.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Compruebe que los dos primeros pasos se hayan completado como se esperaba. Confirme que hay una marca de verificación verde con la palabra **completado**, como se muestra en la figura.
    
     ![Se han completado dos primeros pasos desde la instalación de componentes.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Vuelva a ejecutar **Windows Update** para comprobar si hay alguna actualización después de instalar los componentes de Skype empresarial Server.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Paso 3: solicitar, instalar o asignar certificados

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto al **paso 3: solicitar, instalar o asignar certificados**.
    
    > [!NOTE]
    > Skype empresarial Server incluye compatibilidad con el conjunto de aplicaciones SHA-2 (SHA-2 y longitudes implícitas de 224, 256, 384 o 512 bits) de algoritmos hash y de firma de compendio para conexiones de clientes que ejecutan Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Servidor 2012 o sistemas operativos Windows Server 2008 R2. Para admitir el acceso externo mediante el conjunto de aplicaciones SHA-2, el certificado externo lo emite una entidad de certificación pública que también puede emitir un certificado con el mismo Resumen de longitud de bits. 
  
    > [!IMPORTANT]
    > La selección de qué algoritmo de firma y Resumen de hash depende de los clientes y los servidores que usarán el certificado, y de otros equipos y dispositivos con los que los clientes y servidores se comunicarán con quién también debe saber cómo usar los algoritmos que se usan en el emisor. Para obtener información sobre qué longitudes de síntesis son compatibles en el sistema operativo y en algunas aplicaciones cliente, vea el [blog de Windows PKI-sha2 y Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Cada servidor Standard Edition o front-end requiere hasta cuatro certificados: el certificado oAuthTokenIssuer, un certificado predeterminado, un certificado Web interno y un certificado externo Web. Sin embargo, puede solicitar y asignar un único certificado predeterminado con las entradas de nombre alternativo de sujeto adecuadas, así como el certificado oAuthTokenIssuer. Para obtener más información sobre los requisitos de certificado, consulte [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > El siguiente procedimiento describe cómo configurar certificados desde una entidad de certificación interna basada en servicios de certificados de Active Directory. 
  
2. En la página **Asistente para certificados**, haga clic en **Solicitud**.
    
3. En la página **solicitud de certificado** , rellene los datos pertinentes, incluida la selección del dominio SIP y, a continuación, haga clic en **siguiente**.
    
4. En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente a una entidad de certificación en línea** haciendo clic en **Siguiente**. La CA interna con inscripción en línea automática debe estar disponible si selecciona esta opción. Si elige la opción para retrasar la solicitud, se le pedirá un nombre y una ubicación para guardar el archivo de solicitud de certificado. La solicitud de certificado debe ser presentada y procesada por una CA de su organización o bien por una CA pública. Después, tendrá que importar la respuesta de certificado y asignarla al rol de certificado apropiado.
    
5. En la página elegir una entidad de certificación **(CA)** , seleccione la opción **seleccionar una entidad de certificación de la lista detectada en el entorno** y, a continuación, seleccione una entidad de certificación conocida (mediante registro en los servicios de dominio de Active Directory) de la lista. O bien, seleccione la opción **Especificar otra entidad de certificación**, escriba el nombre de otra CA en el cuadro y haga clic en **Siguiente**.
    
6. En la página **Cuenta de entidad de certificación**, se solicitan sus credenciales para solicitar y procesar la solicitud de certificado en la CA. Debe haber determinado si es necesario un nombre de usuario y una contraseña para solicitar un certificado por adelantado. El administrador de la entidad de certificación tendrá la información necesaria y es posible que tenga que ayudarle en este paso. Si tiene que especificar credenciales alternativas, seleccione la casilla, escriba un nombre de usuario y una contraseña en los cuadros de texto y haga clic en **Siguiente**.
    
7. En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente** para usar la plantilla de servidor web predeterminada.
    
    > [!NOTE]
    > Si su organización ha creado una plantilla para usar como alternativa a la plantilla de la CA de servidor web predeterminada, seleccione la casilla y escriba el nombre de la plantilla alternativa. Necesitará el nombre de la plantilla definido por el administrador de CA. 
  
8. En la página **nombre y configuración de seguridad** , especifique un **nombre descriptivo**. Mediante el uso de un nombre descriptivo, puede identificar rápidamente el certificado y el propósito. Si lo deja en blanco, se generará un nombre automáticamente. Establezca la **Longitud en bits** de la clave o acepte el valor predeterminado de 2048 bits. Seleccione la **clave privada del certificado como exportable** si determina que el certificado y la clave privada se deben mover o copiar a otros sistemas y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Skype empresarial Server tiene requisitos mínimos para una clave privada exportable. Uno de estos sitios se encuentra en los servidores perimetrales en un grupo de servidores, donde el servicio de autenticación relé multimedia usa copias del certificado, en lugar de certificados individuales para cada instancia en el grupo de servidores. 
  
9. En la página **Información de la organización**, si lo desea, proporcione información de la organización y después haga clic en **Siguiente**.
    
10. En la página **Información geográfica**, si lo desea, escriba información geográfica y después haga clic en **Siguiente**.
    
11. En la página **Nombre del sujeto o nombres alternativos del sujeto**, revise los nombres alternativos del sujeto que se van a agregar y haga clic en **Siguiente**.
    
12. En la página **Configuración del dominio SIP**, active la casilla **Dominio SIP** y haga clic en **Siguiente**.
    
13. En la página **Configurar nombres alternativos de sujeto adicionales**, agregue los nombres alternativos de sujeto adicionales que desee, incluido cualquiera que piense que puede ser necesario para dominios SIP adicionales en el futuro, y haga clic en **Siguiente**.
    
14. En la página **Resumen de la solicitud de certificados**, revise la información del resumen. Si la información es correcta, haga clic en **Siguiente**. Si necesita corregir o modificar una configuración, haga clic en **Atrás** para ir a la página pertinente y realizar la corrección o modificación.
    
15. En la página **Ejecución de comandos**, haga clic en **Siguiente**.
    
16. En la página **Estado de solicitud del certificado en línea**, revise la información devuelta. Tenga en cuenta que el certificado se emitió e instaló en el almacén de certificados local. Si se informa de que se ha emitido e instalado, pero no es válido, asegúrese de que el certificado raíz de la CA se haya instalado en el almacén de CA raíz de confianza del servidor. Consulte la documentación de la CA para obtener información sobre cómo recuperar un certificado de CA de raíz de confianza. Si necesita ver el certificado recuperado, haga clic en **Ver detalles del certificado**. De forma predeterminada, la casilla de verificación **asignar el certificado a los usos del certificado de Skype empresarial Server** está seleccionada. Si desea asignar manualmente el certificado, active la casilla y haga clic en **Finalizar**.
    
17. Si ha desactivado la casilla **asignar el certificado a los usos del certificado de Skype empresarial Server** en la página anterior, aparecerá la página asignación de **certificado** . Haga clic en **Siguiente**.
    
18. En la página **Almacén de certificados**, seleccione el certificado solicitado. Si desea ver el certificado, haga clic en **Ver detalles del certificado** y en **Siguiente** para continuar.
    
    > [!NOTE]
    > Si la página de estado de la **solicitud de certificado en línea** notificó un problema con el certificado, como el certificado no es válido, consulte el certificado real para obtener ayuda para resolver el problema. Dos problemas específicos que pueden hacer que un certificado no sea válido son que falte el certificado de CA de raíz de confianza mencionado anteriormente o que falte una clave privada asociada con el certificado. Consulte la documentación de su CA para resolver estos dos problemas.
  
19. En la página **Resumen de asignación de certificados** , revise la información que se presenta para asegurarse de que este sea el certificado que debe asignarse y, a continuación, haga clic en **siguiente**.
    
20. En la página **Ejecutando comandos**, revise el resultado del comando. Haga clic en **Ver registro** si desea revisar el proceso de asignación o si se ha emitido algún error o advertencia. Cuando termine, haga clic en **Finalizar**.
    
21. En la página **Asistente para certificados** , confirme que todos los servicios tienen una marca de verificación verde para indicar que se ha asignado un certificado a todos, incluido el OAuthTokenIssuer, como se muestra en la figura y, a continuación, haga clic en **cerrar**.
    
     ![Certificados instalados y asignados correctamente.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Si va a instalar en un entorno de laboratorio y ha configurado la entidad de certificación con servicios de certificados de Active Directory, tendrá que reiniciar tanto el servidor que ejecuta los servicios de certificados como el servidor front-end antes de que el certificado la asignación puede pasar correctamente. 
  
    > [!TIP]
    >  Para obtener más información acerca de los certificados en servicios de certificados de Active Directory, consulte [servicios de certificados de Active](https://technet.microsoft.com/windowsserver/dd448615.aspx)Directory. 
  
### <a name="step-4-start-services"></a>Paso 4: iniciar servicios

1. Revise los requisitos previos para el **paso 4: iniciar servicios**.
    
2. Si se trata de un grupo de servidores front-end Enterprise Edition con al menos tres servidores, se usa Windows fabric y debe usar el cmdlet **Start-CsPool** . Si se usa un solo servidor, que es siempre el caso de Standard Edition, se utiliza el cmdlet **Start-CsWindowsService** . En este ejemplo, estamos usando Enterprise Edition con tres servidores front-end en el grupo, abra el **Shell de administración de Skype empresarial Server** y ejecute el cmdlet **Start-CsPool** , tal como se muestra en la figura. Para todos los demás roles, incluido el servidor Standard Edition, debe usar **Start-CsWindowsService**. Para implementar roles que no sean el rol front-end, consulte la documentación de esos roles específicos.
    
     ![Inicie los servicios de Skype empresarial.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. En la página **Ejecución de comandos**, una vez que todos los servicios se hayan iniciado correctamente, haga clic en **Finalizar**.
    
    > [!IMPORTANT]
    > El comando para iniciar los servicios en el servidor es un método de mejor esfuerzo para informar de que los servicios tienen, de hecho, iniciado. Es posible que no refleje el estado actual del servicio. Le recomendamos que use el **Estado del servicio Step (opcional)** para abrir Microsoft Management Console (MMC) y confirmar que los servicios se han iniciado correctamente, tal como se muestra en la figura. Si algún servicio de Skype empresarial Server no se ha iniciado, puede hacer clic con el botón secundario en el servicio en MMC y, a continuación, hacer clic en **iniciar**. 
  
     ![Compruebe que los servicios se hayan iniciado.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

