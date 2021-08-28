---
title: Implementar el complemento VDI de Lync con Skype Empresarial Server
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: En este tema se deba a los procedimientos de implementación para usar Skype Empresarial mientras se conecta a un escritorio virtual remoto.
ms.openlocfilehash: 9d745321a398828d6ec31a55528008b467ddea47
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608617"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Implementar el complemento VDI de Lync con Skype Empresarial Server
 
En este tema se deba a los procedimientos de implementación para usar Skype Empresarial mientras se conecta a un escritorio virtual remoto. Las consideraciones de planeación se encuentran en [Plan for Skype Empresarial en entornos VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
Un Infraestructura de escritorio virtual (VDI) se usa en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente confidenciales. Sus usuarios están en equipos Windows locales y usan clientes en un escritorio virtual. El Skype Empresarial en una conexión como esa requiere software de complemento VDI adicional.
  
Hay dos soluciones disponibles para el componente de complemento VDI: una ofrecida por Microsoft y otra ofrecida por Citrix. Microsoft recomienda usar la nueva solución HDX RealTime Optimization Pack en nuevas implementaciones, pero seguirá siendo compatible con el complemento VDI de Lync original durante el resto de su ciclo de vida. 
  
En este tema se proporcionan detalles sobre la implementación del complemento VDI de Microsoft Lync, que solo se admite en Windows 7 y Windows 8 o Windows Server 2008, y solo admite clientes de Lync 2013 o Skype Empresarial. No hay planes para actualizar este complemento, pero [citrix HDX RealTime Optimization Pack](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) para Skype Empresarial se actualizará según sea necesario.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Preparar el entorno para el complemento VDI de Lync
<a name="Prepare_vdi"> </a>

1. En Skype Empresarial Server, asegúrese de que EnableMediaRedirection está establecido en TRUE para todos los usuarios de complementos de Lync VDI. Para obtener más información, consulte los temas de ayuda para el cmdlet [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps) y el cmdlet [Set-CsClientPolicy.](/powershell/module/skype/set-csclientpolicy?view=skype-ps)
    
2. En el servidor del centro de datos, instale el Skype Empresarial en todos los escritorios virtuales.
    
3. En los equipos locales, instale el complemento VDI de Lync.
    
    Los usuarios ahora deben conectar un dispositivo como auriculares o cámara web a su equipo local.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configuración de la conexión de Escritorio remoto
<a name="Prepare_vdi"> </a>

Para preparar la conexión de Escritorio remoto para el complemento VDI de Lync, siga estos pasos en el equipo local:
  
1. Si el equipo local está ejecutando Windows 8, omita este paso. Si el equipo local se ejecuta Windows 7 con SP1, instale la versión Windows 8 del cliente de Servicios [de Escritorio remoto](/windows-server/remote/remote-desktop-services/clients/remote-desktop-clients).
    
2. Inicie el cliente de servicios de escritorio remoto haciendo clic en **Iniciar** y después en **Conexión a escritorio remoto**.
    
3. Haga clic en **Opciones**.
    
4. Haga clic en la pestaña **Recursos locales**. En **Audio remoto**, haga clic en **Configuración** y haga lo siguiente:
    
   - En **Reproducción de audio remota**, seleccione **Reproducir en este equipo**.
    
   - En **Grabación de audio remota**, seleccione **No grabar**.
    
   - Haga clic en **Aceptar**.
    
5. Haga clic en la pestaña **Experiencia**. En **Rendimiento**, desactive la casilla **Almacenamiento en caché persistente de mapas de bits**.
    
6. Haga clic en **la pestaña General.** En **Equipo**, escriba el nombre del escritorio virtual y, a continuación, haga clic **en Conectar**. 
    
## <a name="sign-in-and-use-skype-for-business-on-the-virtual-desktop"></a>Inicie sesión y use Skype Empresarial en el escritorio virtual
<a name="SfB_signin"> </a>

Una vez habilitado el complemento VDI de Lync, el usuario sigue estos pasos al iniciar sesión Skype Empresarial en el escritorio virtual.
  
1. El usuario teme sus credenciales en el Skype Empresarial que se ejecuta en el escritorio virtual.
    
2. Después Skype Empresarial detectar el complemento VDI de Lync, Skype Empresarial solicita al usuario que vuelva a escribir las credenciales. En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para que no tener que escribir las credenciales en inicios de sesión posteriores.
    
3. Skype Empresarial inicia el emparejamiento con el complemento VDI de Lync. Mientras esto sucede, el cliente muestra dos iconos en la Skype Empresarial de estado. El icono de la parte inferior izquierda indica que no hay dispositivos de audio disponibles y el icono parpadeante de la parte inferior derecha indica que el emparejamiento de VDI está en curso: a. Una vez que el emparejamiento de VDI se realiza correctamente, los iconos cambian para indicar el dispositivo de audio que se usará para las llamadas y el emparejamiento de VDI correctamente: b. El usuario ahora puede ver su presencia en Skype Empresarial dispositivos compatibles que están conectados al equipo local y realizar y responder llamadas como de costumbre.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Solucionar problemas del complemento VDI de Lync
<a name="tshoot_VDI"> </a>

Consulte las secciones siguientes si encuentra problemas después de instalar el complemento VDI de Lync.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problemas con la instalación del complemento VDI de Lync

Si hay problemas con la instalación del complemento VDI de Lync, compruebe lo siguiente:
  
- Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.
    
- Asegúrese de que la protección contra la escritura está desactivada. Consulte la documentación del fabricante del dispositivo para obtener instrucciones.
    
### <a name="troubleshooting-issues-with-pairing"></a>Resolución de problemas con el emparejamiento

Cuando se produce un error en el emparejamiento del complemento VDI de Lync, el icono de emparejamiento de la parte inferior derecha se muestra como una "X" roja como se muestra: 
  
Los siguientes son posibles motivos de errores y las acciones que puede realizar para corregir el problema. 
  
- **El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**
    
    El usuario debe cerrar sesión Skype Empresarial e iniciar sesión de nuevo con las credenciales correctas. Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.
    
- **Se está ejecutando otra instancia del cliente de escritorio remoto.**
    
    Si usan la conexión de Escritorio remoto en Windows, los usuarios deben hacer lo siguiente:
    
1. Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.
    
2. Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.
    
3. Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**. 
    
4. Inicie una nueva sesión de escritorio remoto e intente realizar la conexión de nuevo. 
    
- **Los archivos necesarios no se han instalado correctamente.**
    
    Después de instalar el complemento en el equipo local, compruebe que estos archivos están presentes en C:\Archivos de programa\Microsoft Office\Office15 (o la letra de unidad adecuada):
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **El Skype Empresarial se ejecuta en el equipo local.**
    
    Para usar el complemento VDI de Lync, un cliente de Skype Empresarial no debe ejecutarse en el equipo local, de lo contrario se producirá un error en el emparejamiento. Como procedimiento recomendado, el usuario no debe instalar un Skype Empresarial en el equipo local.
    
## <a name="see-also"></a>Consulte también
<a name="tshoot_VDI"> </a>

[Planeación de Skype Empresarial entornos VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md)