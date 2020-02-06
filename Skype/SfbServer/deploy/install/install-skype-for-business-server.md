---
title: Instalar Skype Empresarial Server en los servidores de la topología
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
description: 'Resumen: Aprenda a instalar los componentes del sistema de Skype empresarial Server en cada servidor de la topología. Descargue una prueba gratuita de Skype empresarial Server en el centro de evaluación de Microsoft en https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 8ecf298809a6c4c37b5c075e7ac16623f1669ff9
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41791758"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Instalar Skype Empresarial Server en los servidores de la topología
 
**Resumen:** Obtenga información sobre cómo instalar los componentes del sistema de Skype empresarial Server en cada servidor de la topología. Descargue una prueba gratuita de Skype empresarial Server en el [centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Una vez que se cargue la topología en el almacén de administración central y que Active Directory sepa qué servidores realizarán cada rol, tendrá que instalar el sistema de Skype empresarial Server en cada uno de los servidores de la topología. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos 1 a 5, tal como se indica en el diagrama. Instalar el sistema de Skype empresarial Server es el paso 7 de 8.
  
![Diagrama de información general.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Instalar el sistema de Skype empresarial Server

Una vez que haya publicado una topología, puede instalar los componentes de Skype empresarial Server en cada servidor de la topología. Esta sección le guiará a través de la instalación de Skype empresarial Server y la configuración de los roles de servidor para el grupo de servidores front-end y los roles de servidor que se colocan con los servidores front-end. Para instalar y configurar roles de servidor, ejecute el Asistente para la implementación de Skype empresarial Server en cada equipo en el que esté instalando un rol de servidor. Utilice el Asistente para la implementación para completar los cuatro pasos de este proceso, incluida la instalación del almacén de configuración local, la instalación de los servidores front-end, la configuración de los certificados y la puesta en marcha de los servicios.
  
> [!IMPORTANT]
> Debe usar Topology Builder para completar y publicar la topología antes de instalar Skype empresarial Server en servidores. 
  
> [!NOTE]
> Debe completarse este procedimiento para todos los servidores de la topología. 
  
> [!CAUTION]
> Después de instalar Skype empresarial Server en un servidor front-end, la primera vez que inicie servicios, debe asegurarse de que el servicio Firewall de Windows se esté ejecutando en el servidor. 
  
> [!CAUTION]
> Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que es un administrador local y un miembro del grupo RTCUniversalServerAdmins. 
  
> [!NOTE]
> Si aún no ha ejecutado la configuración de Skype empresarial Server en este servidor, se le pedirá una unidad y una ruta de acceso para la instalación. Esto ofrece la posibilidad de instalarlo en una unidad diferente a la del sistema, en caso de que su organización así lo precise o si tiene problemas de espacio. Puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Skype empresarial Server en el cuadro de diálogo **configuración** a una nueva unidad disponible. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Skype empresarial Server se implementarán también.
  
> [!IMPORTANT]
> Antes de comenzar la instalación, asegúrese de que Windows Server está actualizado mediante Windows Update. 
  
![Windows Server actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Instalar el sistema de Skype empresarial Server

1. Inserte los medios de instalación de Skype empresarial Server. Si la configuración no empieza automáticamente, haga doble clic en **Configuración**.
    
2. La ejecución del soporte de instalación requiere Microsoft Visual C++. Aparecerá un cuadro de diálogo preguntándole si quiere instalarlo. Haga clic en **Sí.**
    
3. Revise cuidadosamente el contrato de licencia y, si está de acuerdo, elija **Acepto los términos del Contrato de licencia** y haga clic en **Aceptar**. 
    
4. La configuración inteligente es una característica de Skype empresarial Server en la que puede conectarse a Internet para comprobar si hay actualizaciones de Microsoft Update (MU) durante el proceso de instalación, tal como se muestra en la ilustración. Esto proporciona una experiencia más gratificante, asegurándose de que tiene las actualizaciones más recientes para el producto. Haga clic en **Instalar** para iniciar la instalación.
    
    > [!NOTE]
    > Muchas organizaciones tienen Windows Server Update Services (WSUS) implementado en sus entornos corporativos. WSUS permite a los administradores administrar por completo la distribución de actualizaciones que se publiquen a través de Microsoft Update en su red. Como parte de la actualización acumulativa 1, Skype empresarial Server presentó compatibilidad para la configuración inteligente para funcionar con WSUS. Los clientes con WSUS que estén implementando Skype empresarial Server por primera vez o que actualicen desde el entorno de Lync Server 2013 con la característica de actualización local capturan las actualizaciones de Skype para Windows de WSUS en lugar de obtener actualizaciones desde MU. Los clientes que deseen usar la configuración inteligente tienen que ejecutar el SmartSetupWithWSUS.psq en todos los equipos antes de ejecutar Setup.exe. 
  
     ![Captura de pantalla de configuración inteligente](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. En la página Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Skype empresarial Server**.
    
6. Realice los procedimientos de los procedimientos siguientes, cuando haya terminado, haga clic en **salir** para cerrar el Asistente para la implementación. Repita los procedimientos para cada servidor front-end del grupo.
    
### <a name="step-1-install-local-configuration-store"></a>Paso 1: Instalar almacén de configuración local

1. Revise los requisitos previos y haga clic en **Ejecutar**, junto a **Paso 1: Instalar almacén de configuración local**.
    
    > [!NOTE]
    > El almacén de configuración local es una copia de solo lectura del Almacén de administración central. En una implementación Standard Edition, el Almacén de administración central se crea con una copia local de SQL Server Express Edition en el servidor front-end al ejecutarse el procedimiento Preparar el primer servidor de Standard Edition. En una implementación de Enterprise Edition, el Almacén de administración central se crea cuando se publica una topología que incluya un grupo front-end Enterprise Edition. 
  
2. En la página **Instalar almacén de configuración local**, asegúrese de que la opción **Recuperar directamente del Almacén de administración central** esté seleccionada y luego haga clic en **Siguiente**.
    
    SQL Server Express Edition, que es necesario para el almacén de configuración local, se instala en el servidor local.
    
3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Paso 2: configurar o quitar los componentes de Skype empresarial Server

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto al **paso 2: configurar o quitar los componentes de Skype empresarial Server**.
    
2. En la página **Configurar componentes de Skype empresarial Server** , haga clic en **siguiente** para configurar los componentes tal como se definen en la topología publicada.
    
3. La página **Ejecución de comandos** muestra un resumen de los comandos, así como también información sobre la instalación a medida que se realiza. Cuando termine, puede usar la lista para seleccionar un registro para ver y, a continuación, hacer clic en **Ver registro**.
    
4. Cuando termine la instalación de los componentes de Skype empresarial y haya revisado los registros según sea necesario, haga clic en **Finalizar** para completar este paso en la instalación.
    
    > [!NOTE]
    > Reinicie el servidor si se le pide (puede ser el caso si fue necesario instalar la Experiencia de escritorio de Windows). Cuando el equipo vuelva a estar en funcionamiento, tendrá que ejecutar este procedimiento (paso 2: instalar o quitar los componentes de Skype empresarial Server) de nuevo. 
  
    > [!NOTE]
    > Si el instalador detecta que no se cumple algún requisito previo, se lo comunicará por medio de un mensaje ("Requisito previo no satisfecho") como el de la figura. Cumpla con los requisitos previos necesarios y, a continuación, inícielo (paso 2: instalar o quitar los componentes de Skype empresarial Server) otra vez. 
  
     ![Prerrequisito necesario.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Compruebe que los dos primeros pasos se han completado del modo esperado. Confirme que hay una marca de verificación verde con la palabra **Completado**, como se muestra en la figura.
    
     ![Primeros dos pasos de la instalación de componentes completos.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Ejecute **Windows Update** de nuevo para comprobar si hay actualizaciones después de instalar los componentes de Skype empresarial Server.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Paso 3: Solicitar, instalar o asignar certificados

1. Revise los requisitos previos y haga clic en **Ejecutar**, junto a **Paso 3: Solicitar, instalar o asignar certificados**.
    
    > [!NOTE]
    > Skype empresarial Server incluye compatibilidad con el conjunto de programas SHA-2 (SHA-2, que usa longitud de compendio de 224, 256, 384 o 512 bits) de algoritmos de firma y hash de síntesis para conexiones de clientes que ejecutan Windows 10, Windows 8, Windows 7, Windows Server 2012, Windows Server 2012 o en sistemas operativos Windows Server 2008 R2. Para permitir el acceso externo mediante el conjunto de aplicaciones SHA-2, el certificado externo lo emite una CA pública que también puede emitir un certificado con las mismas longitudes de bits de síntesis. 
  
    > [!IMPORTANT]
    > La selección de la síntesis de hash y el algoritmo de firma depende de los clientes y de los servidores que usarán el certificado y de otros equipos y dispositivos con los que los clientes y servidores se comunicarán, quienes también deben saber cómo usar los algoritmos del certificado. Para obtener información sobre qué longitudes de compendio se admiten en el sistema operativo y en algunas aplicaciones cliente, consulte [blog de Windows PKI-sha2 y Windows](https://go.microsoft.com/fwlink/p/?LinkId=287002). 
  
    Cada servidor Standard Edition o front-end necesita hasta cuatro certificados: el certificado oAuthTokenIssuer, un certificado predeterminado, un certificado web interno y un certificado web externo. Pero, es posible solicitar y asignar un solo certificado predeterminado con las entradas de nombre alternativo de sujeto apropiadas, así como el certificado oAuthTokenIssuer. Para obtener más información sobre los requisitos de certificado, consulte [requisitos ambientales para Skype empresarial Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [requisitos del servidor para skype empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > El siguiente procedimiento describe cómo configurar certificados de una entidad de certificación interna basada en Servicios de certificados de Active Directory. 
  
2. En la página **Asistente para certificados**, haga clic en **Solicitar**.
    
3. En la página **Solicitud de certificado**, rellene los datos necesarios, incluida la selección de dominio SIP, y haga clic en **Siguiente**.
    
4. En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente a una entidad de certificación en línea** haciendo clic en **Siguiente**. La CA interna con inscripción en línea automática debe estar disponible si selecciona esta opción. Si elige la opción para retrasar la solicitud, se le pedirá un nombre y una ubicación para guardar el archivo de solicitud de certificado. La solicitud de certificado debe ser presentada y procesada por una CA de su organización o bien por una CA pública. Después, tendrá que importar la respuesta de certificado y asignarla al rol de certificado apropiado.
    
5. En la página elegir una entidad emisora de **certificados (CA)** , seleccione la opción **seleccionar una CA de la lista detectada en su entorno** y, a continuación, seleccione una CA conocida (mediante registro en servicios de dominio de Active Directory) de la lista. O bien, seleccione la opción **Especificar otra entidad de certificación** escriba el nombre de otra CA en el cuadro y haga clic en **Siguiente**.
    
6. En la página **Cuenta de la entidad de certificación**, se solicitan sus credenciales para solicitar y procesar la solicitud de certificado en la CA. Es necesario que haya determinado si es necesario un nombre de usuario y una contraseña para solicitar un certificado por adelantado. Su administrador de CA tendrá la información necesaria y es posible que tenga que ayudarle en este paso. Si tiene que especificar credenciales alternativas, active la casilla, escriba un nombre de usuario y una contraseña en los cuadros de texto y haga clic en **Siguiente**.
    
7. En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente** para usar la plantilla de servidor web predeterminada.
    
    > [!NOTE]
    > Si su organización ha creado una plantilla para usar como alternativa a la plantilla de la CA de servidor web predeterminada, seleccione la casilla y escriba el nombre de la plantilla alternativa. Necesitará el nombre de la plantilla definido por el administrador de CA. 
  
8. En la página **nombre y configuración de seguridad** , especifique un **nombre descriptivo**. Al usar un nombre descriptivo, puede identificar rápidamente el certificado y el propósito. Si deja el campo en blanco, se generará un nombre automáticamente. Establezca la **longitud de bit** de la tecla o acepte el valor predeterminado de 2048 bits. Seleccione la **clave privada del certificado como exportable** si determina que el certificado y la clave privada se deben mover o copiar a otros sistemas y, a continuación, haga clic en **siguiente**.
    
    > [!NOTE]
    > Skype empresarial Server tiene los requisitos mínimos para una clave privada exportable. Uno de estos sitios se encuentra en los servidores perimetrales en un grupo de servidores, donde el servicio de autenticación relé multimedia usa copias del certificado, en lugar de certificados individuales para cada instancia en el grupo de servidores. 
  
9. En la página **Información de la organización**, si lo desea, proporcione información de la organización y después haga clic en **Siguiente**.
    
10. En la página **Información geográfica**, si lo desea, escriba información geográfica y después haga clic en **Siguiente**.
    
11. En la página **Nombre del sujeto/Nombres alternativos del juego**, revise los nombres alternativos del sujeto que se van a agregar y haga clic en **Siguiente**.
    
12. En la página **Configuración del dominio SIP**, active la casilla **Dominio SIP** y haga clic en **Siguiente**.
    
13. En la página **Configurar nombres alternativos de sujeto adicionales**, agregue los nombres alternativos de sujeto adicionales que desee, incluido cualquiera que piense que puede ser necesario para dominios SIP adicionales en el futuro, y haga clic en **Siguiente**.
    
14. En la página **Resumen de la solicitud de certificados**, revise la información del resumen. Si la información es correcta, haga clic en **Siguiente**. Si necesita corregir o modificar una configuración, haga clic en **Atrás** para ir a la página pertinente y realizar la corrección o modificación.
    
15. En la página **Ejecución de comandos**, haga clic en **Siguiente**.
    
16. On the **Online Certificate Request Status** page, review the information returned. You should note that the certificate was issued and installed into the local certificate store. Si se informa que ha sido emitido e instalado, pero no es válido, asegúrese de que el certificado raíz de la CA se ha instalado en el almacén de CA raíz de confianza del servidor. Refer to your CA documentation on how to retrieve a Trusted Root CA certificate. If you need to view the retrieved certificate, click **View Certificate Details**. De forma predeterminada, está seleccionada la casilla de verificación **asignar el certificado a los usos del certificado de Skype empresarial Server** . If you want to manually assign the certificate, clear the check box, and then click **Finish**.
    
17. Si desactivó la casilla para **asignar el certificado a los usos del certificado de Skype empresarial Server** en la página anterior, se le presentará la página **asignación de certificado** . Click **Next**.
    
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
    >  Para obtener más información sobre los certificados en servicios de certificados de Active Directory, vea [servicios de certificados de Active](https://technet.microsoft.com/en-us/windowsserver/dd448615.aspx)Directory. 
  
### <a name="step-4-start-services"></a>Paso 4: Iniciar los servicios

1. Revise los requisitos del **Paso 4: Iniciar servicios**.
    
2. If this is an Enterprise Edition Front End pool with at least three servers, Windows Fabric is used, and you must use the **Start-CsPool** cmdlet. Si se usa un solo servidor, lo cual es siempre el caso de Standard Edition, se usa el cmdlet **Start-CsWindowsService** . En este ejemplo usamos Enterprise Edition con tres servidores front-end en el grupo, abra el **Shell de administración de Skype empresarial Server** y ejecute el cmdlet **Start-CsPool** como se muestra en la ilustración. For all other roles, including Standard Edition server, you must use **Start-CsWindowsService**. To deploy roles other than the Front End role, see documentation for those particular roles.
    
     ![Inicia los servicios de Skype Empresarial.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. En la página **Ejecución de comandos**, una vez que todos los servicios se hayan iniciado correctamente, haga clic en **Finalizar**.
    
    > [!IMPORTANT]
    > El comando para iniciar los servicios en el servidor es un método de mejor esfuerzo para informar de que los servicios, efectivamente, se han iniciado. Es posible que no refleje el estado actual del servicio. Recomendamos llevar a cabo el paso **Estado del servicio (opcional)** para abrir Microsoft Management Console (MMC) y confirmar que los servicios se han iniciado correctamente, como se indica en la figura. Si algún servicio de Skype empresarial Server no se ha iniciado, puede hacer clic con el botón secundario del ratón en el servicio en la MMC y, a continuación, hacer clic en **iniciar**. 
  
     ![Ha comenzado la verificación de servicios.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
  

