---
title: Implementar el complemento VDI para Lync con Skype empresarial Server
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: krishra
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 11d3bd5d-6dd3-471c-b842-b072fa197714
description: En este tema se describen los procedimientos de implementación para usar Skype empresarial mientras se conecta a un escritorio virtual remoto.
ms.openlocfilehash: f864136ab55f37a9bfaf54d6c31d74d31844da59
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768953"
---
# <a name="deploy-the-lync-vdi-plug-in-with-skype-for-business-server"></a>Implementar el complemento VDI para Lync con Skype empresarial Server
 
En este tema se describen los procedimientos de implementación para usar Skype empresarial mientras se conecta a un escritorio virtual remoto. Las consideraciones de planeación están en el [plan de Skype empresarial en entornos de VDI](../../plan-your-deployment/clients-and-devices/vdi-environments.md).
  
El entorno de Infraestructura de escritorio virtual (VDI) se utiliza en algunas organizaciones donde los problemas de seguridad y cumplimiento son especialmente delicados. Sus usuarios se encuentran en equipos Windows locales y utilizan clientes en un escritorio virtual. Usar Skype empresarial en una conexión como esta requiere software de complemento VDI adicional.
  
Hay dos soluciones disponibles para el componente de complemento VDI: una ofrecida por Microsoft y la otra ofrecida por Citrix. Microsoft recomienda usar la nueva solución de paquete de optimización en tiempo real de HDX en implementaciones nuevas, pero continuará con el complemento de VDI original de Lync durante el resto de su ciclo de vida. 
  
Este tema proporciona detalles sobre cómo implementar el complemento Microsoft Lync VDI, que solo se admite en Windows 7 y Windows 8 o Windows Server 2008, y solo admite clientes de Lync 2013 o Skype empresarial. No hay planes de actualizar este complemento, pero el [paquete de optimización en tiempo real de Citrix HDX](../../plan-your-deployment/clients-and-devices/vdi-environments.md#Citrix_RT) se actualizará según sea necesario.
  
## <a name="prepare-your-environment-for-the-lync-vdi-plug-in"></a>Prepare su entorno para el complemento Lync VDI
<a name="Prepare_vdi"> </a>

1. En Skype empresarial Server, asegúrese de que EnableMediaRedirection se establece en TRUE para todos los usuarios del complemento VDI para Lync. Para obtener más información, consulte los temas de ayuda para el cmdlet [New-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps) y el cmdlet [set-ClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps) .
    
2. En el servidor del centro de datos, instale el cliente de Skype empresarial en todos los escritorios virtuales.
    
3. En los equipos locales, instale el complemento VDI de Lync.
    
    Ahora, los usuarios deberían conectar un dispositivo como un auricular o una cámara web a sus equipos locales.
    
## <a name="configure-remote-desktop-connection-settings"></a>Configure los parámetros de conexión a Escritorio remoto
<a name="Prepare_vdi"> </a>

Para preparar la conexión a escritorio remoto para el complemento VDI de Lync, siga estos pasos en el equipo local:
  
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

Después de habilitar el complemento VDI para Lync, el usuario sigue estos pasos al iniciar sesión en Skype empresarial en el escritorio virtual.
  
1. El usuario escribe sus credenciales en el cliente de Skype empresarial que se ejecuta en el escritorio virtual.
    
2. Una vez que Skype empresarial detecta el complemento VDI para Lync, Skype empresarial solicita al usuario que vuelva a escribir las credenciales. En este cuadro de diálogo, conviene seleccionar la casilla **Guardar mi contraseña** para no tener que escribir las credenciales en inicios de sesión posteriores.
    
3. Skype empresarial comienza a emparejarse con el complemento VDI de Lync. Mientras eso sucede, el cliente muestra dos iconos en la barra de estado de Skype empresarial. El icono de la esquina inferior izquierda indica que no hay dispositivos de audio disponibles, y el icono parpadeante en la esquina inferior derecha indica que el emparejamiento de VDI está en curso: a. Después de que el emparejamiento de VDI se haya realizado correctamente, los iconos cambian para indicar el dispositivo de audio que se usará para las llamadas y el éxito del emparejamiento de VDI: b. Ahora, el usuario puede ver su presencia en dispositivos compatibles con Skype empresarial que están conectados al equipo local, y realizar y contestar llamadas de la forma habitual.
    
## <a name="troubleshoot-the-lync-vdi-plug-in"></a>Solucione problemas del complemento Lync VDI
<a name="tshoot_VDI"> </a>

Consulte las siguientes secciones si experimenta algún problema después de instalar el complemento Lync VDI.
  
### <a name="issues-with-installing-the-lync-vdi-plug-in"></a>Problemas con la instalación del complemento Lync VDI 

Si hay problemas con la instalación del complemento de VDI para Lync, compruebe lo siguiente:
  
- Asegúrese de que hay espacio suficiente en la carpeta especificada en las variables del sistema TEMP y TMP.
    
- Asegúrese de que la protección contra la escritura está desactivada. Consulte la documentación del fabricante del dispositivo para obtener instrucciones.
    
### <a name="troubleshooting-issues-with-pairing"></a>Resolución de problemas con el emparejamiento

Cuando se produce un error en el complemento VDI de Lync, el icono de emparejamiento en la esquina inferior derecha se muestra como una "X" de color rojo, como se muestra a continuación: 
  
A continuación se describen algunas posibles razones de los errores, así como las acciones que puede llevar a cabo para solucionar el problema.  
  
- **El usuario ha especificado credenciales incorrectas durante el inicio de sesión.**
    
    El usuario debe cerrar la sesión de Skype empresarial e iniciarla de nuevo con las credenciales correctas. Volverá a aparecer el cuadro de diálogo de emparejamiento para mostrar si el emparejamiento se ha llevado a cabo correctamente.
    
- **Se está ejecutando otra instancia del cliente de escritorio remoto.**
    
    Si usan conexión a escritorio remoto en Windows, los usuarios deben hacer lo siguiente:
    
1. Inicie el Administrador de tareas: presione **Alt+Ctrl+Suprimir** y haga clic en **Iniciar el Administrador de tareas**.
    
2. Haga clic en la pestaña **Procesos** y busque en la lista todos los procesos con el nombre **mstsc.exe**.
    
3. Resalte cada uno de los procesos **mstsc.exe** y haga clic en **Finalizar proceso**.  
    
4. Inicie una nueva sesión de escritorio remoto e intente establecer la conexión de nuevo.  
    
- **Los archivos necesarios no se han instalado correctamente.**
    
    Una vez instalado el complemento en el equipo local, asegúrese de que los siguientes archivos estén presentes en el directorio C:\Archivos de programa\Microsoft Office\Office15 (o la letra de la unidad que corresponda):
    
  - LyncVdiPlugin.dll
    
  - UcVdi.dll
    
- **El cliente de Skype empresarial se está ejecutando en el equipo local.**
    
    Para usar el complemento VDI para Lync, un cliente de Skype empresarial no debe estar ejecutándose en el equipo local; de lo contrario, se producirá un error de emparejamiento. Como práctica recomendada, el usuario no debe instalar un cliente de Skype empresarial en el equipo local.
    
## <a name="see-also"></a>Vea también
<a name="tshoot_VDI"> </a>

[Plan for Skype for Business in VDI environments](../../plan-your-deployment/clients-and-devices/vdi-environments.md)
