---
title: Instalar Skype Empresarial Server en servidores de la topología
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumen: obtenga información sobre cómo instalar los componentes del sistema de Skype Empresarial Server en cada servidor de la topología. Descargue una prueba gratuita de Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: e6aa1dde01f7f91b7d1c18b1664a3658911cf50b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801690"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Instalar Skype Empresarial Server en servidores de la topología
 
**Resumen:** Obtenga información sobre cómo instalar los componentes del sistema de Skype Empresarial Server en cada servidor de la topología. Descargue una versión de prueba gratuita de Skype Empresarial Server desde el Centro [de evaluación de Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Una vez que la topología se carga en el Almacén de administración central y Active Directory sabe qué servidores realizarán los roles, debe instalar el sistema de Skype Empresarial Server en cada uno de los servidores de la topología. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5, tal como se indica en el diagrama. La instalación del sistema de Skype Empresarial Server es el paso 7 de 8.
  
![Diagrama de información general.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Instalar el sistema de Skype Empresarial Server

Una vez que haya publicado una topología, puede instalar los componentes de Skype Empresarial Server en cada servidor de la topología. Esta sección le guiará a través de la instalación de Skype Empresarial Server y la configuración de los roles de servidor para el grupo de servidores front-end y los roles de servidor que se instalan con los servidores front-end. Para instalar y configurar roles de servidor, ejecute el Asistente para la implementación de Skype Empresarial Server en cada equipo en el que va a instalar un rol de servidor. Use el Asistente para la implementación para completar los cuatro pasos de implementación, incluida la instalación del almacén de configuración local, la instalación de los servidores front-end, la configuración de certificados y el inicio de servicios.
  
> [!IMPORTANT]
> Debe usar el Generador de topologías para completar y publicar la topología antes de instalar Skype Empresarial Server en los servidores. 
  
> [!NOTE]
> Este procedimiento debe completarse para todos los servidores de la topología. 
  
> [!CAUTION]
> Después de instalar Skype Empresarial Server en un servidor front-end, la primera vez que inicie los servicios, debe asegurarse de que el servicio Firewall de Windows se ejecuta en el servidor. 
  
> [!CAUTION]
> Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que sea administrador local y miembro del grupo RTCUniversalServerAdmins. 
  
> [!NOTE]
> If you haven't run Skype for Business Server setup on this server before, you'll be prompted for a drive and path for the installation. Esto proporciona la capacidad de instalarse en una unidad que no sea la unidad del sistema, si su organización lo requiere o si tiene problemas de espacio. Puede cambiar la ruta de acceso de ubicación  de instalación de los archivos de Skype Empresarial Server en el cuadro de diálogo de instalación a una nueva unidad disponible. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, el resto de los archivos de Skype Empresarial Server también se implementarán allí.
  
> [!IMPORTANT]
> Antes de comenzar la instalación, asegúrate de que Windows Server esté actualizado mediante Windows Update. 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Instalar el sistema de Skype Empresarial Server

1. Inserte los medios de instalación de Skype Empresarial Server. Si la configuración no se inicia automáticamente, haga doble clic en **El programa de instalación.**
    
2. El medio de instalación requiere que se ejecute Microsoft Visual C++. Aparecerá un cuadro de diálogo que le preguntará si desea instalarlo. Haga **clic en Sí.**
    
3. Revise cuidadosamente el Contrato de licencia y, si está de acuerdo, seleccione **Acepto** los términos del contrato de licencia y haga clic en **Aceptar.** 
    
4. La configuración inteligente es una característica de Skype Empresarial Server en la que puede conectarse a Internet para buscar actualizaciones de Microsoft Update (MU) durante el proceso de instalación, como se muestra en la figura. Esto proporciona una mejor experiencia al asegurarte de que tienes las actualizaciones más recientes para el producto. Haga clic en **Instalar** para comenzar el proceso de instalación.
    
    > [!NOTE]
    > Muchas organizaciones tienen Windows Server Update Services (WSUS) implementado en sus entornos corporativos. WSUS permite a los administradores administrar completamente la distribución de las actualizaciones que se lanzan a través de Microsoft Update en los equipos de su red. Como parte de la versión de actualización acumulativa 1, Skype Empresarial Server introdujo compatibilidad con la configuración inteligente para trabajar con WSUS. Los clientes con WSUS que implementan Skype Empresarial Server por primera vez o actualicen desde el entorno de Lync Server 2013 con la característica de actualización de In-Place tendrán la configuración inteligente recuperando actualizaciones de Skype para Windows desde WSUS en lugar de obtener actualizaciones de MU. Los clientes que quieran usar la configuración inteligente deben ejecutar SmartSetupWithWSUS.psq en todos los equipos antes de ejecutar Setup.exe. 
  
     ![Captura de pantalla de configuración inteligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. En la página Asistente para la implementación, haga clic **en Instalar o actualizar el sistema de Skype Empresarial Server.**
    
6. Realice los procedimientos de los procedimientos siguientes, cuando los haya completado, haga clic en **Salir** para cerrar el Asistente para la implementación. Repita los procedimientos para cada servidor front-end del grupo.
    
### <a name="step-1-install-local-configuration-store"></a>Paso 1: Instalar el almacén de configuración local

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto al **paso 1: Instalar almacén de configuración local.**
    
    > [!NOTE]
    > El almacén de configuración local es una copia de solo lectura del Almacén de administración central. En una implementación Standard Edition, el Almacén de administración central se crea con una copia local de SQL Server Express Edition en el servidor front-end. Esto sucede cuando se ejecuta el procedimiento Preparar el primer servidor Standard Edition. En una implementación de Enterprise Edition, el almacén de administración central se crea cuando se publica la topología que incluye un grupo de servidores front-end Enterprise Edition. 
  
2. En la página Instalar almacén de  configuración **local,** asegúrese de que la opción Recuperar directamente desde el almacén de administración central está seleccionada y, a continuación, haga clic en **Siguiente.**
    
    SQL Server Express Edition se instala en el servidor local. SQL Server Express Edition es necesario para el almacén de configuración local.
    
3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Paso 2: Configurar o quitar componentes de Skype Empresarial Server

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto al **paso 2:** Instalar o quitar componentes de Skype Empresarial Server.
    
2. En la página Configurar componentes de  Skype Empresarial **Server,** haga clic en Siguiente para configurar los componentes según se define en la topología publicada.
    
3. La **página Ejecutar comandos muestra** un resumen de los comandos y la información de instalación a medida que se lleva a cabo la configuración. Cuando haya terminado, puede usar la lista para seleccionar un registro que desea ver y, a continuación, hacer clic **en Ver registro.**
    
4. Cuando finalice la instalación de los componentes de Skype Empresarial Server  y haya revisado los registros según sea necesario, haga clic en Finalizar para completar este paso en la instalación.
    
    > [!NOTE]
    > Reinicie el servidor si se le solicita (lo que puede ocurrir si es necesario instalar la experiencia de escritorio de Windows). Cuando el equipo esté en funcionamiento, deberá volver a ejecutar este procedimiento (Paso 2: Instalar o quitar componentes de Skype Empresarial Server). 
  
    > [!NOTE]
    > Si el instalador encuentra algún requisito previo que no se haya cumplido, se le notificará con un mensaje "Requisito previo no satisfecho", como se muestra en la figura. Cumpla los requisitos previos necesarios y, a continuación, vuelva a iniciar este procedimiento (Paso 2: Instalar o quitar componentes de Skype Empresarial Server). 
  
     ![Requisito previo necesario.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Compruebe que los dos primeros pasos se completaron como se esperaba. Confirme que hay una marca de verificación verde con la palabra **Complete**, como se muestra en la ilustración.
    
     ![Los dos primeros pasos completados a partir de la instalación de componentes.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Vuelva **a ejecutar Windows Update** para comprobar si hay actualizaciones después de instalar los componentes de Skype Empresarial Server.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Paso 3: Solicitar, instalar o asignar certificados

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto al **paso 3: Solicitar, instalar o asignar certificados.**
    
    > [!NOTE]
    > Skype Empresarial Server incluye compatibilidad con el conjunto de aplicaciones SHA-2 (SHA-2 usa longitudes implícitas de 224, 256, 384 o 512 bits) de algoritmos hash de síntesis y algoritmos de firma para las conexiones de clientes que ejecutan los sistemas operativos Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2. Para admitir el acceso externo mediante el conjunto de aplicaciones SHA-2, el certificado externo lo emite una CA pública que también puede emitir un certificado con la misma síntesis de longitud de bits. 
  
    > [!IMPORTANT]
    > La selección del algoritmo de firma y síntesis hash depende de los clientes y los servidores que usarán el certificado, así como de otros equipos y dispositivos con los que los clientes y servidores se comunicarán y que también deben saber cómo usar los algoritmos usados en el certificado. Para obtener información sobre las longitudes implícitas que se admiten en el sistema operativo y algunas aplicaciones cliente, consulta el blog de PKI de [Windows: SHA2 y Windows.](https://go.microsoft.com/fwlink/p/?LinkId=287002) 
  
    Cada servidor Standard Edition o front-end requiere hasta cuatro certificados: el certificado oAuthTokenIssuer, un certificado predeterminado, un certificado interno web y un certificado externo web. Sin embargo, puede solicitar y asignar un único certificado predeterminado con entradas de nombre alternativo de sujeto apropiadas, así como el certificado oAuthTokenIssuer. Para obtener más información sobre los requisitos de certificado, consulte Requisitos del entorno [para Skype Empresarial Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o requisitos de servidor para Skype Empresarial Server [2019.](../../../SfBServer2019/plan/system-requirements.md)
    
    > [!IMPORTANT]
    > El siguiente procedimiento describe cómo configurar certificados de una entidad de certificación interna basada en Servicios de certificados de Active Directory. 
  
2. En la página **Asistente para certificados**, haga clic en **Solicitud**.
    
3. En la **página Solicitud de** certificado, rellene los datos relevantes, incluida la selección del dominio SIP y haga clic en **Siguiente.**
    
4. En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente a una entidad de certificación en línea** haciendo clic en **Siguiente**. La CA interna con inscripción en línea automática debe estar disponible si selecciona esta opción. Si elige la opción para retrasar la solicitud, se le pedirá un nombre y una ubicación para guardar el archivo de solicitud de certificado. La solicitud de certificado debe ser presentada y procesada por una CA de su organización o bien por una CA pública. Después, tendrá que importar la respuesta de certificado y asignarla al rol de certificado apropiado.
    
5. En la página Elegir una entidad de certificación **(CA),** seleccione la opción Seleccionar una CA de la lista detectada en su entorno y, **a** continuación, seleccione una CA conocida (mediante el registro en Servicios de dominio de Active Directory) de la lista. O bien, seleccione la opción **Especificar otra entidad de certificación**, escriba el nombre de otra CA en el cuadro y haga clic en **Siguiente**.
    
6. En la página **Cuenta de entidad de certificación**, se solicitan sus credenciales para solicitar y procesar la solicitud de certificado en la CA. Debe haber determinado si es necesario un nombre de usuario y una contraseña para solicitar un certificado por adelantado. El administrador de la entidad de certificación tendrá la información necesaria y es posible que tenga que ayudarle en este paso. Si tiene que especificar credenciales alternativas, seleccione la casilla, escriba un nombre de usuario y una contraseña en los cuadros de texto y haga clic en **Siguiente**.
    
7. En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente** para usar la plantilla de servidor web predeterminada.
    
    > [!NOTE]
    > Si su organización ha creado una plantilla para usar como alternativa a la plantilla de la CA de servidor web predeterminada, seleccione la casilla y escriba el nombre de la plantilla alternativa. Necesitará el nombre de la plantilla definido por el administrador de CA. 
  
8. En la **página Nombre y configuración de** seguridad, especifique un nombre **descriptivo.** Mediante el uso de un nombre descriptivo, puede identificar rápidamente el certificado y el propósito. Si lo deja en blanco, se generará un nombre automáticamente. Establezca la **Longitud en bits** de la clave o acepte el valor predeterminado de 2048 bits. Seleccione marcar la clave privada del certificado como **exportable** si determina que el certificado y la clave privada deben moverse o copiarse a otros sistemas y, a continuación, haga clic en **Siguiente**.
    
    > [!NOTE]
    > Skype Empresarial Server tiene requisitos mínimos para una clave privada exportable. Uno de estos sitios se encuentra en los servidores perimetrales en un grupo de servidores, donde el servicio de autenticación relé multimedia usa copias del certificado, en lugar de certificados individuales para cada instancia en el grupo de servidores. 
  
9. En la página **Información de la organización**, si lo desea, proporcione información de la organización y después haga clic en **Siguiente**.
    
10. En la página **Información geográfica**, si lo desea, escriba información geográfica y después haga clic en **Siguiente**.
    
11. En la página **Nombre del sujeto o nombres alternativos del sujeto**, revise los nombres alternativos del sujeto que se van a agregar y haga clic en **Siguiente**.
    
12. En la página **Configuración del dominio SIP**, active la casilla **Dominio SIP** y haga clic en **Siguiente**.
    
13. En la página **Configurar nombres alternativos de sujeto adicionales**, agregue los nombres alternativos de sujeto adicionales que desee, incluido cualquiera que piense que puede ser necesario para dominios SIP adicionales en el futuro, y haga clic en **Siguiente**.
    
14. En la página **Resumen de la solicitud de certificados**, revise la información del resumen. Si la información es correcta, haga clic en **Siguiente**. Si necesita corregir o modificar una configuración, haga clic en **Atrás** para ir a la página pertinente y realizar la corrección o modificación.
    
15. En la página **Ejecución de comandos**, haga clic en **Siguiente**.
    
16. En la página **Estado de solicitud del certificado en línea**, revise la información devuelta. Tenga en cuenta que el certificado se emitió e instaló en el almacén de certificados local. Si se informa de que se ha emitido e instalado, pero no es válido, asegúrese de que el certificado raíz de ca se ha instalado en el almacén de ca raíz de confianza del servidor. Consulte la documentación de la CA para obtener información sobre cómo recuperar un certificado de CA de raíz de confianza. Si necesita ver el certificado recuperado, haga clic en **Ver detalles del certificado**. De forma predeterminada, la casilla asignar el certificado a **los usos** de certificados de Skype Empresarial Server está activada. Si desea asignar manualmente el certificado, active la casilla y haga clic en **Finalizar**.
    
17. Si ha desactivado la casilla asignar el certificado a los **usos** de certificados de Skype Empresarial Server en la página anterior, aparecerá la página **Asignación de** certificados. Haga clic en **Siguiente**.
    
18. En la página **Almacén de certificados**, seleccione el certificado solicitado. Si desea ver el certificado, haga clic en **Ver detalles del certificado** y en **Siguiente** para continuar.
    
    > [!NOTE]
    > Si la **página Estado de** solicitud de certificado en línea informó de un problema con el certificado, como que el certificado no es válido, vea el certificado real para obtener ayuda para resolver el problema. Dos problemas específicos que pueden hacer que un certificado no sea válido son que falte el certificado de CA de raíz de confianza mencionado anteriormente o que falte una clave privada asociada con el certificado. Consulte la documentación de su CA para resolver estos dos problemas.
  
19. En la **página Resumen de asignación** de certificados, revise la información que se presenta para asegurarse de que se trata del certificado que se debe asignar y, a continuación, haga clic en **Siguiente**.
    
20. En la página **Ejecutando comandos**, revise el resultado del comando. Haga clic en **Ver registro** si desea revisar el proceso de asignación o si se ha emitido algún error o advertencia. Cuando termine, haga clic en **Finalizar**.
    
21. En  la página Asistente para certificados, confirme que todos los servicios tienen una comprobación verde para indicar que se ha asignado un certificado a todos, incluido el OAuthTokenIssuer , como se muestra en la ilustración, y, a continuación, haga clic en Cerrar **.**
    
     ![Certificados instalados y asignados correctamente.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Si va a instalar en un entorno de laboratorio y acaba de configurar la entidad de certificación mediante servicios de certificados de Active Directory, deberá reiniciar el servidor que ejecuta Servicios de certificados y también el servidor front-end para que la asignación de certificados pueda completarse correctamente. 
  
    > [!TIP]
    >  Para obtener más información acerca de los certificados de Servicios de certificados de Active Directory, vea [Servicios de certificados de Active Directory.](https://technet.microsoft.com/windowsserver/dd448615.aspx) 
  
### <a name="step-4-start-services"></a>Paso 4: Iniciar servicios

1. Revise los requisitos previos del **paso 4: Iniciar servicios.**
    
2. Si se trata de un grupo de servidores front-end Enterprise Edition con al menos tres servidores, se usa Windows Fabric y debe usar el cmdlet **Start-CsPool.** Si se usa un único servidor, que siempre es el caso de Standard Edition, use el cmdlet **Start-CsWindowsService.** En este ejemplo, estamos usando Enterprise Edition con tres servidores front-end en el grupo de servidores, abra el Shell de administración de Skype Empresarial **Server** y ejecute el cmdlet **Start-CsPool,** como se muestra en la figura. Para todos los demás roles, incluido el servidor Standard Edition, debe usar **Start-CsWindowsService**. Para implementar roles distintos del rol front-end, consulte la documentación de esos roles concretos.
    
     ![Inicie los servicios de Skype Empresarial.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. En la página **Ejecución de comandos**, una vez que todos los servicios se hayan iniciado correctamente, haga clic en **Finalizar**.
    
    > [!IMPORTANT]
    > El comando para iniciar los servicios en el servidor es un método de mejor esfuerzo para informar de que, de hecho, los servicios se han iniciado. Es posible que no refleje el estado actual del servicio. Se recomienda usar el paso Estado del servicio **(opcional)** para abrir Microsoft Management Console (MMC) y confirmar que los servicios se han iniciado correctamente, como se muestra en la figura. Si no se ha iniciado ningún servicio de Skype Empresarial Server, puede hacer clic con el botón secundario en ese servicio en MMC y, a continuación, hacer clic en **Iniciar.** 
  
     ![Compruebe que se han iniciado los servicios.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

