---
title: Implementación del complemento Lync VDI con Skype para Business Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: En este tema se describe los procedimientos de implementación para el uso de Skype para la empresa mientras se conecta a un escritorio virtual remoto.
ms.openlocfilehash: 94539a263fb88f4c1306bbc87de665bf7d985fe1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895289"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Implementación del complemento Lync VDI con Skype para Business Server
 
En este tema se describe los procedimientos de implementación para el uso de Skype para la empresa mientras se conecta a un escritorio virtual remoto. Consideraciones de planeación se encuentran en la [planeación de Skype para la empresa en entornos de VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
El entorno de Infraestructura de escritorio virtual (VDI) se utiliza en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente delicados. Sus usuarios se encuentran en equipos Windows locales y utilizan clientes en un escritorio virtual. Usar Skype para la empresa en una conexión como el que requiere el software adicional de complemento de VDI.
  
Existen dos soluciones disponibles para el componente de complemento de VDI - uno ofrecida por Microsoft y uno ofrecidos por Citrix. Microsoft recomienda el uso de la nueva solución de HDX en tiempo real Optimization Pack en las nuevas implementaciones, pero seguirá siendo compatible con el complemento de VDI de Lync original para el resto de su ciclo de vida. 
  
En este tema se proporciona información detallada sobre la implementación de Microsoft Lync VDI Plug-in, que sólo se admite en Windows 7 y Windows 8 o Windows Server 2008 y sólo es compatible con Lync 2013 o Skype para clientes empresariales. No existen planes para actualizar este complemento, pero el [Paquete de optimización de Citrix HDX en tiempo real](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) de Skype para la empresa se actualizarán según sea necesario.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Prepare su entorno para el complemento Lync VDI
<a name="Prepare_vdi"> </a>

1. En Skype para Business Server, asegúrese de que enablemediaredirection tiene en TRUE para todos los usuarios de Lync VDI Plug-in. Para obtener información detallada, vea los temas de ayuda para el cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) y el cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .
    
2. En el servidor del centro de datos, instale el Skype para cliente de negocio en todos los equipos de escritorio virtuales.
    
3. En los equipos locales, instale el complemento de VDI Lync.
    
    Ahora, los usuarios deberían conectar un dispositivo como un auricular o una cámara web a sus equipos locales.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configure los parámetros de conexión a Escritorio remoto
<a name="Prepare_vdi"> </a>

Para preparar la conexión a Escritorio remoto para el complemento de VDI Lync, siga estos pasos en el equipo local:
  
1. Si el equipo local está ejecutando Windows 8, omita este paso. Si el equipo local ejecuta Windows 7 con SP1, instale la versión más reciente de Windows 8 del [cliente de servicios de escritorio remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032).
    
2. Inicie el cliente de Servicios de Escritorio remoto haciendo clic en **Iniciar** y después en **Conexión a Escritorio remoto**.
    
3. Haga clic en **Opciones**.
    
4. Haga clic en la pestaña **Recursos locales**. En **Audio remoto**, haga clic en **Configuración** y haga lo siguiente:
    
   - En **Reproducción de audio remoto**, seleccione **Reproducir en este equipo**.
    
   - En **Grabación de audio remoto**, seleccione **No grabar**.
    
   - Haga clic en **Aceptar**.
    
5. Haga clic en la pestaña **Experiencia**. En **Rendimiento**, desactive la casilla **Almacenamiento en caché persistente de mapas de bits**.
    
6. Haga clic en la pestaña **General**. En **Equipo**, escriba el nombre del escritorio virtual y haga clic en **Conectar**.  
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Inicie sesión en Skype Empresarial y úselo en el escritorio virtual
<a name="SfB_signin"> </a>

Después de habilitar el complemento de VDI Lync, el usuario sigue estos pasos al iniciar sesión Skype para la empresa en el escritorio virtual.
  
1. El usuario escribe sus credenciales en a la Skype para clientes empresariales que se ejecutan en el escritorio virtual.
    
2. Después de Skype para la empresa detecta del complemento Lync VDI, Skype para la empresa solicita al usuario que vuelva a escribir las credenciales. En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para no tener que escribir las credenciales en inicios de sesión posteriores.
    
3. Skype para la empresa comienza el emparejamiento con el complemento de VDI Lync. Mientras que sucede, el cliente muestra dos iconos en el Skype para la barra de estado de negocio. El icono en la parte inferior izquierda indica que no hay dispositivos de audio están disponibles, y el icono intermitente en la esquina inferior derecha indica que el emparejamiento VDI está en curso: un. Después de que el emparejamiento de VDI es correcto, los iconos cambian para indicar el dispositivo de audio que se usará para las llamadas y el emparejamiento de VDI: b. Ahora, el usuario puede ver su presencia en Skype para dispositivos compatibles de negocio que están conectados al equipo local y realizar y responder llamadas como de costumbre.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Solucione problemas del complemento Lync VDI
<a name="tshoot_VDI"> </a>

Consulte las siguientes secciones si experimenta algún problema después de instalar el complemento Lync VDI.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problemas con la instalación del complemento Lync VDI 

Si hay problemas con la instalación del complemento Lync VDI, compruebe lo siguiente:
  
- Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.
    
- Asegúrese de que la protección contra la escritura está desactivada. Consulte la documentación del fabricante de su dispositivo para obtener instrucciones.
    
### <a name="troubleshooting-issues-with-pairing"></a>Resolución de problemas con el emparejamiento

Cuando el emparejamiento de complemento Lync VDI se produce un error, el icono de emparejamiento en la parte inferior derecha mostrará como una "X" roja como se muestra: 
  
A continuación se describen algunas posibles razones de los errores, así como las acciones que puede llevar a cabo para solucionar el problema.  
  
- **El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**
    
    El usuario debe cerrar la sesión de Skype para la empresa e iniciar sesión de nuevo con las credenciales correctas. Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.
    
- **Se está ejecutando otra instancia del cliente de escritorio remoto.**
    
    Si están usando conexión a Escritorio remoto en Windows, los usuarios deben hacer lo siguiente:
    
1. Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.
    
2. Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.
    
3. Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**.  
    
4. Inicie una nueva sesión de escritorio remoto e intente establecer la conexión de nuevo.  
    
- **Los archivos necesarios no se han instalado correctamente.**
    
    Una vez instalado el complemento en el equipo local, asegúrese de que los siguientes archivos estén presentes en el directorio C:\Archivos de programa\Microsoft Office\Office15 (o la letra de la unidad que corresponda):
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **El Skype para clientes empresariales se está ejecutando en el equipo local.**
    
    Para usar el complemento, que no debe ejecutar un Skype para clientes empresariales en el equipo local de Lync VDI, el apareamiento de lo contrario se producirá un error. Como procedimiento recomendado, el usuario no debe instalar un Skype para clientes empresariales en el equipo local.
    
## <a name="see-also"></a>Vea también
<a name="tshoot_VDI"> </a>

[Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
