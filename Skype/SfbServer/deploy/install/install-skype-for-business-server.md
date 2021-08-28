---
title: Instalar Skype Empresarial Server servidores en la topología
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: defd6b2c-f267-4f8c-bc94-8894e2a429b6
description: 'Summary: Learn how to install the Skype Empresarial Server system components on each server in the topology. Descargue una versión de prueba Skype Empresarial Server desde el Centro de evaluación de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 89c158243a0cc33faaa1a3b3181dfc1f39094d63
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58609867"
---
# <a name="install-skype-for-business-server-on-servers-in-the-topology"></a>Instalar Skype Empresarial Server servidores en la topología
 
**Resumen:** Obtenga información sobre cómo instalar los Skype Empresarial Server del sistema en cada servidor de la topología. Descargue una prueba gratuita de Skype Empresarial Server desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Una vez que la topología se carga en el Almacén de administración central y Active Directory sabe qué servidores realizarán los roles, debe instalar el sistema Skype Empresarial Server en cada uno de los servidores de la topología. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después de los pasos del 1 al 5 tal como se describe en el diagrama. Instalar el Skype Empresarial Server es el paso 7 de 8.
  
![Diagrama de información general.](../../media/6855713d-a5b4-4e5b-8f83-fef3d7a5ec5d.png)
  
## <a name="install-skype-for-business-server-system"></a>Instalar Skype Empresarial Server sistema

Una vez que haya publicado una topología, puede instalar los componentes Skype Empresarial Server en cada servidor de la topología. Esta sección le guía a través de la instalación de Skype Empresarial Server y la configuración de los roles de servidor para el grupo de servidores front-end y los roles de servidor que se instalan con los servidores front-end. Para instalar y configurar roles de servidor, ejecute el Asistente para la implementación Skype Empresarial Server en cada equipo en el que va a instalar un rol de servidor. Use el Asistente para la implementación para completar los cuatro pasos de implementación, como instalar el almacén de configuración local, instalar los servidores front-end, configurar certificados e iniciar servicios.
  
> [!IMPORTANT]
> Debe usar el Generador de topologías para completar y publicar la topología antes de poder instalar Skype Empresarial Server servidores. 
  
> [!NOTE]
> Este procedimiento debe completarse para todos los servidores de la topología. 
  
> [!CAUTION]
> Después de instalar Skype Empresarial Server en un servidor front-end, la primera vez que inicie los servicios, debe asegurarse de que el servicio de firewall Windows se está ejecutando en el servidor. 
  
> [!CAUTION]
> Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que sea administrador local y miembro del grupo RTCUniversalServerAdmins. 
  
> [!NOTE]
> Si no ha ejecutado Skype Empresarial Server instalación en este servidor antes, se le pedirá una unidad y una ruta de acceso para la instalación. Esto proporciona la capacidad de instalar en una unidad que no sea la unidad del sistema, si su organización lo requiere o si tiene problemas de espacio. Puede cambiar la ruta de ubicación de instalación  de los archivos Skype Empresarial Server en el cuadro de diálogo Instalación a una unidad nueva y disponible. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, el resto de los Skype Empresarial Server también se implementarán allí.
  
> [!IMPORTANT]
> Antes de comenzar la instalación, asegúrese de que Windows Server esté actualizado mediante Windows Update. 
  
![Windows Servidor actualizado.](../../media/a8d57a97-a55e-443b-b304-c534ae9a71b2.png)
  
### <a name="install-skype-for-business-server-system"></a>Instalar Skype Empresarial Server sistema

1. Inserte el Skype Empresarial Server de instalación. Si la configuración no se inicia automáticamente, haga doble clic en **Configurar**.
    
2. El medio de instalación Microsoft Visual C++ para ejecutarse. Aparecerá un cuadro de diálogo que le preguntará si desea instalarlo. Haga clic **en Sí.**
    
3. Revise detenidamente el Contrato de licencia y, si está de acuerdo, seleccione **Acepto** los términos del contrato de licencia y haga clic en **Aceptar**. 
    
4. Smart Setup es una característica de Skype Empresarial Server donde puede conectarse a Internet para buscar actualizaciones de Microsoft Update (MU) durante el proceso de instalación, como se muestra en la figura. Esto proporciona una mejor experiencia al asegurarse de que tiene las actualizaciones más recientes para el producto. Haga clic en **Instalar** para comenzar el proceso de instalación.
    
    > [!NOTE]
    > Muchas organizaciones han Windows Server Update Services (WSUS) implementadas en sus entornos corporativos. WSUS permite a los administradores administrar completamente la distribución de las actualizaciones que se liberan a través de Microsoft Update en los equipos de su red. Como parte de la versión acumulativa de la actualización 1, Skype Empresarial Server se introdujo compatibilidad para que smart setup funcione con WSUS. Los clientes con WSUS que están implementando Skype Empresarial Server por primera vez o actualizando desde el entorno de Lync Server 2013 con la característica de actualización de In-Place tendrán la configuración inteligente recuperando Skype para las actualizaciones de Windows de WSUS en lugar de obtener actualizaciones de MU. Los clientes que quieran usar smart setup deben ejecutar SmartSetupWithWSUS.psq en todas las máquinas antes de ejecutar Setup.exe. 
  
     ![Captura de pantalla del programa de instalación inteligente.](../../media/d35c6cd9-3b8d-4510-871c-30ad07b1f4f2.png)
  
5. En la página Asistente para implementación, haga clic **en Instalar o actualizar Skype Empresarial Server sistema**.
    
6. Realice los procedimientos en los siguientes procedimientos, cuando los haya completado, haga clic en **Salir** para cerrar el Asistente para implementación. Repita los procedimientos para cada servidor front-end del grupo.
    
### <a name="step-1-install-local-configuration-store"></a>Paso 1: Instalar el almacén de configuración local

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto a **Paso 1: Instalar almacén de configuración local**.
    
    > [!NOTE]
    > El Almacén de configuración local es una copia de solo lectura del Almacén de administración central. En una Standard Edition, el Almacén de administración central se crea con una copia local de SQL Server Express Edition en el servidor front-end. Esto sucede cuando se ejecuta el procedimiento Prepare First Standard Edition Server. En una Enterprise Edition, el almacén de administración central se crea al publicar la topología que incluye un grupo Enterprise Edition front-end. 
  
2. En la **página Instalar almacén de configuración local,** asegúrese de que está seleccionada la opción Recuperar directamente desde el almacén de administración **central** y, a continuación, haga clic en **Siguiente**.
    
    SQL Server Express Edition se instala en el servidor local. SQL Server Express La edición es necesaria para el almacén de configuración local.
    
3. Una vez completado el proceso de instalación de configuración del servidor local, haga clic en **Finalizar**.
    
### <a name="step-2-setup-or-remove-skype-for-business-server-components"></a>Paso 2: Configurar o quitar Skype Empresarial Server componentes

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto a **Paso 2: Configurar** o Quitar Skype Empresarial Server componentes .
    
2. En la **página Configurar componentes Skype Empresarial Server,** haga clic en Siguiente para configurar los componentes tal como se definen en la topología publicada. 
    
3. La **página Ejecutar comandos** muestra un resumen de los comandos y la información de instalación a medida que se lleva a cabo la configuración. Cuando haya terminado, puede usar la lista para seleccionar un registro que desea ver y, a continuación, haga clic **en Ver registro**.
    
4. Cuando Skype Empresarial Server la instalación de componentes y haya revisado los registros  según sea necesario, haga clic en Finalizar para completar este paso en la instalación.
    
    > [!NOTE]
    > Reinicie el servidor si se le solicita (lo que puede ocurrir si Windows se necesita instalar la experiencia de escritorio). Cuando el equipo está haciendo una copia de seguridad y en ejecución, debe volver a ejecutar este procedimiento (Paso 2: Configurar o quitar Skype Empresarial Server componentes). 
  
    > [!NOTE]
    > Si el instalador encuentra algún requisito previo que no se haya cumplido, se le notificará con un mensaje "Requisito previo no satisfecho", como se muestra en la figura. Cumpla el requisito previo necesario y vuelva a iniciar este procedimiento (Paso 2: Configurar o quitar Skype Empresarial Server componentes). 
  
     ![Requisito previo necesario.](../../media/21a84dfe-70ff-4f76-bd7e-41032660200a.png)
  
5. Compruebe que los dos primeros pasos se completaron según lo esperado. Confirme que hay una marca de verificación verde con la palabra **Complete**, como se muestra en la figura.
    
     ![Los dos primeros pasos completados a partir de la instalación de componentes.](../../media/59851804-d805-4fa8-854b-60c3de2d109f.png)
  
6. Ejecute **Windows Update** de nuevo para comprobar si hay actualizaciones después de instalar el Skype Empresarial Server componentes.
    
### <a name="step-3-request-install-or-assign-certificates"></a>Paso 3: Solicitar, instalar o asignar certificados

1. Revise los requisitos previos y, a continuación, haga clic en **Ejecutar** junto al **paso 3: Solicitar, instalar o asignar certificados**.
    
    > [!NOTE]
    > Skype Empresarial Server incluye compatibilidad con el conjunto sha-2 (SHA-2 usa longitudes implícitas de 224, 256, 384 o 512 bits) de algoritmos de hash y firma implícita para conexiones de clientes que ejecutan los sistemas operativos Windows 10, Windows 8, Windows 7, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2. Para admitir el acceso externo con el conjunto de aplicaciones SHA-2, una CA pública emite el certificado externo que también puede emitir un certificado con el mismo resumen de longitud de bits. 
  
    > [!IMPORTANT]
    > La selección del algoritmo de síntesis hash y firma depende de los clientes y los servidores que usarán el certificado, así como de otros equipos y dispositivos con los que los clientes y servidores se comunicarán, que también deben saber cómo usar los algoritmos usados en el certificado. Para obtener información sobre qué longitudes implícitas son compatibles con el sistema operativo y algunas aplicaciones cliente, vea Windows [blog de PKI : SHA2 y Windows](/archive/blogs/pki/sha2-and-windows). 
  
    Cada Standard Edition servidor front-end requiere hasta cuatro certificados: el certificado oAuthTokenIssuer, un certificado predeterminado, un certificado interno web y un certificado externo web. Sin embargo, puede solicitar y asignar un único certificado predeterminado con entradas de nombre alternativo de sujeto adecuadas, así como el certificado oAuthTokenIssuer. Para obtener más información acerca de los requisitos de certificado, [vea Requisitos](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) del entorno para Skype Empresarial Server o Requisitos de servidor [para Skype Empresarial Server 2019](../../../SfBServer2019/plan/system-requirements.md).
    
    > [!IMPORTANT]
    > En el siguiente procedimiento se describe cómo configurar certificados de una entidad de certificación interna basada en Servicios de certificados de Active Directory. 
  
2. En la página **Asistente para certificados**, haga clic en **Solicitud**.
    
3. En la **página Solicitud de** certificado, rellene los datos relevantes, incluida la selección del dominio SIP y , haga clic en **Siguiente**.
    
4. En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente a una entidad de certificación en línea** haciendo clic en **Siguiente**. La CA interna con inscripción en línea automática debe estar disponible si selecciona esta opción. Si elige la opción para retrasar la solicitud, se le pedirá un nombre y una ubicación para guardar el archivo de solicitud de certificado. La solicitud de certificado debe ser presentada y procesada por una CA de su organización o bien por una CA pública. Después, tendrá que importar la respuesta de certificado y asignarla al rol de certificado apropiado.
    
5. En la página Elegir una entidad de certificación **(CA),** seleccione la opción Seleccionar una CA de la lista detectada en el entorno y, a continuación, seleccione una **CA** conocida (mediante el registro en Servicios de dominio de Active Directory) de la lista. O bien, seleccione la opción **Especificar otra entidad de certificación**, escriba el nombre de otra CA en el cuadro y haga clic en **Siguiente**.
    
6. En la página **Cuenta de entidad de certificación**, se solicitan sus credenciales para solicitar y procesar la solicitud de certificado en la CA. Debe haber determinado si es necesario un nombre de usuario y una contraseña para solicitar un certificado por adelantado. El administrador de la ENTIDAD de certificación tendrá la información necesaria y puede que tenga que ayudarle en este paso. Si tiene que especificar credenciales alternativas, seleccione la casilla, escriba un nombre de usuario y una contraseña en los cuadros de texto y haga clic en **Siguiente**.
    
7. En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente** para usar la plantilla de servidor web predeterminada.
    
    > [!NOTE]
    > Si su organización ha creado una plantilla para usar como alternativa a la plantilla de la CA de servidor web predeterminada, seleccione la casilla y escriba el nombre de la plantilla alternativa. Necesitará el nombre de la plantilla definido por el administrador de CA. 
  
8. En la **página Nombre y Configuración** seguridad, especifique un nombre **descriptivo**. Al usar un nombre descriptivo, puede identificar rápidamente el certificado y el propósito. Si lo deja en blanco, se generará un nombre automáticamente. Establezca la **Longitud en bits** de la clave o acepte el valor predeterminado de 2048 bits. Seleccione marcar la clave privada del certificado como **exportable** si determina que el certificado y la clave privada deben moverse o copiarse en otros sistemas y, a continuación, haga clic en **Siguiente**.
    
    > [!NOTE]
    > Skype Empresarial Server requisitos mínimos para una clave privada exportable. Uno de estos sitios se encuentra en los servidores perimetrales en un grupo de servidores, donde el servicio de autenticación relé multimedia usa copias del certificado, en lugar de certificados individuales para cada instancia en el grupo de servidores. 
  
9. En la página **Información de la organización**, si lo desea, proporcione información de la organización y después haga clic en **Siguiente**.
    
10. En la página **Información geográfica**, si lo desea, escriba información geográfica y después haga clic en **Siguiente**.
    
11. En la página **Nombre del sujeto o nombres alternativos del sujeto**, revise los nombres alternativos del sujeto que se van a agregar y haga clic en **Siguiente**.
    
12. En la página **Configuración del dominio SIP**, active la casilla **Dominio SIP** y haga clic en **Siguiente**.
    
13. En la página **Configurar nombres alternativos de sujeto adicionales**, agregue los nombres alternativos de sujeto adicionales que desee, incluido cualquiera que piense que puede ser necesario para dominios SIP adicionales en el futuro, y haga clic en **Siguiente**.
    
14. En la página **Resumen de la solicitud de certificados**, revise la información del resumen. Si la información es correcta, haga clic en **Siguiente**. Si necesita corregir o modificar una configuración, haga clic en **Atrás** para ir a la página pertinente y realizar la corrección o modificación.
    
15. En la página **Ejecución de comandos**, haga clic en **Siguiente**.
    
16. En la página **Estado de solicitud del certificado en línea**, revise la información devuelta. Tenga en cuenta que el certificado se emitió e instaló en el almacén de certificados local. Si se notifica que se ha emitido e instalado, pero no es válido, asegúrese de que el certificado raíz de ca se ha instalado en el almacén de ca raíz de confianza del servidor. Consulte la documentación de la CA para obtener información sobre cómo recuperar un certificado de CA de raíz de confianza. Si necesita ver el certificado recuperado, haga clic en **Ver detalles del certificado**. De forma predeterminada, está activada la casilla Asignar el certificado a **Skype Empresarial Server usos de** certificados. Si desea asignar manualmente el certificado, active la casilla y haga clic en **Finalizar**.
    
17. Si ha desactivado la casilla Asignar el certificado **Skype Empresarial Server usos** de certificados en la página anterior, se le mostrará la página **Asignación de** certificados. Haga clic en **Siguiente**.
    
18. En la página **Almacén de certificados**, seleccione el certificado solicitado. Si desea ver el certificado, haga clic en **Ver detalles del certificado** y en **Siguiente** para continuar.
    
    > [!NOTE]
    > Si la **página Estado de solicitud** de certificado en línea ha notificado un problema con el certificado, como que el certificado no es válido, vea el certificado real para obtener ayuda para resolver el problema. Dos problemas específicos que pueden hacer que un certificado no sea válido son que falte el certificado de CA de raíz de confianza mencionado anteriormente o que falte una clave privada asociada con el certificado. Consulte la documentación de su CA para resolver estos dos problemas.
  
19. En la **página Resumen de asignación** de certificados, revise la información presentada para asegurarse de que este es el certificado que se debe asignar y, a continuación, haga clic en **Siguiente**.
    
20. En la página **Ejecutando comandos**, revise el resultado del comando. Haga clic en **Ver registro** si desea revisar el proceso de asignación o si se ha emitido algún error o advertencia. Cuando termine, haga clic en **Finalizar**.
    
21. En  la página Asistente para certificados, confirme que todos los servicios tienen una comprobación verde para indicar que se ha asignado un certificado a todos, incluido el OAuthTokenIssuer , como se muestra en la figura y, a continuación, haga clic en **Cerrar**.
    
     ![Certificados instalados y asignados correctamente.](../../media/d8e1911c-d096-4f88-97a9-d2a704defa17.png)
  
    > [!TIP]
    > Si está instalando en un entorno de laboratorio y acaba de configurar la entidad de certificación con Servicios de certificados de Active Directory, deberá reiniciar el servidor que ejecuta Servicios de certificados y también el servidor front-end antes de que la asignación de certificados pueda realizarse correctamente. 
  
    > [!TIP]
    >  Para obtener más información acerca de los certificados en Servicios de certificados de Active Directory, vea [Servicios de certificados de Active Directory](/windows/deployment/deploy-whats-new). 
  
### <a name="step-4-start-services"></a>Paso 4: Iniciar servicios

1. Revise los requisitos previos **del Paso 4: Iniciar servicios**.
    
2. Si se trata de un Enterprise Edition front-end con al menos tres servidores, Windows Fabric se usa y debe usar el cmdlet **Start-CsPool.** Si se usa un solo servidor, que siempre es el caso de Standard Edition, use el cmdlet **Start-CsWindowsService.** En este ejemplo, estamos usando Enterprise Edition con tres servidores front-end en el grupo de servidores, abra el Shell de administración de **Skype Empresarial Server** y ejecute el cmdlet **Start-CsPool** como se muestra en la figura. Para todos los demás roles, incluido Standard Edition servidor, debe usar **Start-CsWindowsService**. Para implementar roles distintos del rol front-end, consulte la documentación de esos roles concretos.
    
     ![Inicie Skype Empresarial servicios.](../../media/f52ec719-9476-419f-9a78-df08368395f7.png)
  
3. En la página **Ejecución de comandos**, una vez que todos los servicios se hayan iniciado correctamente, haga clic en **Finalizar**.
    
    > [!IMPORTANT]
    > El comando para iniciar los servicios en el servidor es el mejor método de esfuerzo para informar de que los servicios, de hecho, se han iniciado. Es posible que no refleje el estado actual del servicio. Se recomienda usar el paso Estado del servicio **(opcional)** para abrir Microsoft Management Console (MMC) y confirmar que los servicios se han iniciado correctamente, como se muestra en la figura. Si algún Skype Empresarial Server no se ha iniciado, puede hacer clic con el botón secundario en ese servicio en MMC y, a continuación, hacer clic en **Inicio**. 
  
     ![Compruebe que los servicios se han iniciado.](../../media/47906fb7-9d37-4d55-8d8d-e5a4a2366510.png)
