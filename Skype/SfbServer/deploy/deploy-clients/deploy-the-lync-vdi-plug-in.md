---
title: Implementar el complemento Lync VDI con Skype Empresarial Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: Este tema describen los procedimientos de implementación para utilizar Skype para el negocio al conectarse a un escritorio virtual remoto.
ms.openlocfilehash: a8f95903f3c06fd953b8d97ba829d4f23e8d72b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server-2015"></a>Implementar el complemento Lync VDI con Skype Empresarial Server 2015
 
Este tema describen los procedimientos de implementación para utilizar Skype para el negocio al conectarse a un escritorio virtual remoto. 
  
El entorno de Infraestructura de escritorio virtual (VDI) se utiliza en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente delicados. Sus usuarios se encuentran en equipos Windows locales y utilizan clientes en un escritorio virtual. Usando Skype para el negocio en una conexión que requiere software adicional de Plug-in de VDI.
  
Existen dos soluciones disponibles para el componente de complemento de VDI - uno ofrecidos por Microsoft y otro ofrecido por Citrix. Microsoft recomienda el uso de la nueva solución HDX RealTime Optimization Pack en nuevas implementaciones, pero seguirá siendo compatible con el complemento de VDI Lync original para el resto de su ciclo de vida. 
  
Este tema proporciona detalles sobre la implementación de Microsoft Lync VDI Plug-in, que sólo se admite en Windows 7 y Windows 8 o Windows Server 2008 y sólo es compatible con Lync 2013 o Skype para clientes de negocios 2015. No hay planes para actualizar este complemento, pero el [Paquete de optimización de Citrix HDX en tiempo real](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) de Skype para empresas se actualizarán según sea necesario.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Prepare su entorno para el complemento Lync VDI
<a name="Prepare_vdi"> </a>

1. En Skype para Business Server 2015, asegúrese de que EnableMediaRedirection está establecido en TRUE para todos los usuarios de Plug-in de Lync VDI. Para obtener más información, vea los temas de ayuda para el cmdlet [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) y el cmdlet [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .
    
2. En el servidor de centro de datos, instale el Skype para cliente de negocios 2015 en todos los escritorios virtuales.
    
3. En los equipos locales, instale el plug-in de VDI Lync.
    
    Ahora, los usuarios deberían conectar un dispositivo como un auricular o una cámara web a sus equipos locales.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configure los parámetros de conexión a Escritorio remoto
<a name="Prepare_vdi"> </a>

Para preparar la VDI Lync complemento conexión a Escritorio remoto, siga estos pasos en el equipo local:
  
1. Si el equipo local ejecuta Windows 8, omita este paso. Si el equipo local ejecuta Windows 7 con SP1, instale la versión 8 de Windows más reciente del [cliente de servicios de escritorio remoto](https://go.microsoft.com/fwlink/p/?LinkId=268032).
    
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

Después de habilitar el complemento de VDI Lync, el usuario sigue estos pasos al iniciar sesión en Skype para el año 2015 de negocio en el escritorio virtual.
  
1. El usuario escribe sus credenciales en para el Skype para 2015 de negocio cliente que se ejecuta en el escritorio virtual.
    
2. Una vez Skype para negocios 2015 detecta el plug-in de VDI Lync, Skype para negocios 2015 pide al usuario que vuelva a escribir las credenciales. En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para no tener que escribir las credenciales en inicios de sesión posteriores.
    
3. Skype para negocios 2015 comienza el emparejamiento con el plug-in de VDI de Lync. Mientras Eso sucede, el cliente muestra dos iconos en el Skype para negocios 2015 barra de estado. El icono que aparece en la parte inferior izquierda indica que no hay dispositivos de audio disponibles y el icono intermitente en la parte inferior derecha, que el emparejamiento de VDI está en curso:
    4. Una vez realizado el emparejamiento de VDI, los iconos cambian para indicar el dispositivo de audio que se utilizará para las llamadas y el emparejamiento de VDI:
    5. Ahora el usuario puede ver su presencia en Skype para negocios 2015 dispositivos compatibles que están conectados al equipo local y colocarán y responder a las llamadas como de costumbre.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Solucione problemas del complemento Lync VDI
<a name="tshoot_VDI"> </a>

Consulte las siguientes secciones si experimenta algún problema después de instalar el complemento Lync VDI.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problemas con la instalación del complemento Lync VDI 

Si hay problemas al instalar el complemento de VDI Lync, compruebe lo siguiente:
  
- Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.
    
- Asegúrese de que la protección contra la escritura está desactivada. Consulte la documentación del fabricante de su dispositivo para obtener instrucciones.
    
### <a name="troubleshooting-issues-with-pairing"></a>Resolución de problemas con el emparejamiento

Cuando Lync VDI complemento sincronización falla, el icono de emparejamiento en el inferior derecho se muestra como una "X" roja como se muestra: 
  
A continuación se describen algunas posibles razones de los errores, así como las acciones que puede llevar a cabo para solucionar el problema.  
  
- **El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**
    
    El usuario debe cerrar la sesión de Skype para empresas y vuelve a identificarte con las credenciales correctas. Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.
    
- **Se está ejecutando otra instancia del cliente de escritorio remoto.**
    
    Si están usando conexión a Escritorio remoto en Windows, los usuarios deberían hacer lo siguiente:
    
1. Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.
    
2. Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.
    
3. Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**.  
    
4. Inicie una nueva sesión de escritorio remoto e intente establecer la conexión de nuevo.  
    
- **Los archivos necesarios no se han instalado correctamente.**
    
    Una vez instalado el complemento en el equipo local, asegúrese de que los siguientes archivos estén presentes en el directorio C:\Archivos de programa\Microsoft Office\Office15 (o la letra de la unidad que corresponda):
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **El Skype para 2015 de negocio cliente está ejecutando en el equipo local.**
    
    Para utilizar el complemento, que un Skype para cliente de negocios 2015 no debe ejecutarse en el equipo local de VDI Lync, emparejamiento de lo contrario se producirá un error. Como práctica recomendada, el usuario no debe instalar un Skype para 2015 de negocio cliente en el equipo local.
    
## <a name="see-also"></a>Vea también
<a name="tshoot_VDI"> </a>

#### 

[Plan de Skype para el negocio en entornos de VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md)

