---
title: Configurar una consola de Sistemas de salas de Skype v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/14/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection: Strat_SB_Admin
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: En este artículo se describe cómo configurar el dispositivo de consola de los Sistemas de sala de Skype v2 y sus periféricos.
ms.openlocfilehash: eed37791c73b2deeb9e5f0605dbf1265d9a1d02d
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19501028"
---
# <a name="configure-a-skype-room-systems-v2-console"></a>Configurar una consola de Sistemas de salas de Skype v2
 
En este artículo se describe cómo configurar el dispositivo de consola de los Sistemas de sala de Skype v2 y sus periféricos.
  
Sólo debe realizar estos pasos si el Skype es necesario para las cuentas empresariales y de Exchange ya se han creado y probado tal como se describe en [implementar sistemas de salón de Skype v2](room-systems-v2.md). Necesitará el hardware y software descritos en [requisitos de sistemas de salón de Skype v2](../../plan-your-deployment/clients-and-devices/requirements.md). Este tema incluye las secciones siguientes:
  
- [Preparación de la imagen de instalación](console.md#Prep_Image)
    
- [Instalar un certificado de entidad de certificación privado en el dispositivo de tableta](console.md#Certs)
    
- [Instalar Windows 10 y la aplicación de consola de v2 de sistemas de salón de Skype](console.md#Reimage)
   
- [Configuración inicial de la consola](console.md#Initial)
    
- [Lista de comprobación de implementación de v2 de sistemas de salón de Skype](console.md#Checklist)
    
> [!NOTE]
> Sistemas de salón de Skype v2 sólo funciona en un Skype configurada correctamente para el entorno empresarial donde las cuentas de dispositivos estén configuradas correctamente, tal como se describe en [implementar sistemas de salón de Skype v2](room-systems-v2.md). 
  
## <a name="prepare-the-installation-image"></a>Preparación de la imagen de instalación
<a name="Prep_Image"> </a>

Instalar la aplicación v2 de sistemas de salón de Skype en un Surface Pro 4 o Surface Pro requiere un dispositivo de almacenamiento USB con al menos 32GB de memoria con formato de un disco FAT32. No debe haber ningún otro archivo en el dispositivo, se perderán todos los archivos existentes en el almacenamiento USB. 
  
> [!NOTE]
> Si no se lograr crear la imagen de consola de acuerdo con estas instrucciones, el resultado probablemente será un comportamiento inesperado. Actualización de aniversario de empresa de Windows 10 (versión 1607) ya no se admite para la creación de sistemas de salón de Skype v2 imagen. 
  
> [!NOTE]
> Funcionará un v2 de Skype salón sistemas existentes con Windows 10 Enterprise aniversario de actualización de mover a sistemas de salón de Skype v2 actualización 3 mediante el almacén de Windows, pero se debe realizar una nueva instalación tal y como se describe a continuación. 
  
1. Descargue la [MSU para KB4056892](http://download.windowsupdate.com/c/msdownload/update/software/secu/2018/01/windows10.0-kb4056892-x64_a41a378cf9ae609152b505c40e691ca1228e28ea.msu).
2. Descargar el [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
3. Colocar la MSU para KB4056892 en el mismo directorio que la secuencia de comandos CreateSrsMedia.ps1.
4. Ejecute el script CreateSrsMedia.ps1 desde un símbolo del sistema con privilegios elevados en un equipo Windows 10.


Siga las instrucciones de la secuencia de comandos para crear un disco de instalación de sistemas de salón de Skype v2 USB. Cuando haya terminado, quitar el disco USB de su equipo y proceda a [instalar 10 de Windows y la aplicación de consola de sistemas de salón de Skype v2 ](console.md#Reimage).
    
## <a name="install-windows-10-and-the-skype-room-systems-v2-console-app"></a>Instalación de Windows 10 y la aplicación de consola Sistemas de salas de Skype 
<a name="Reimage"> </a>

En este momento, deberá aplicar la imagen que ha creado. La tableta se ejecutará como un dispositivo y el usuario predeterminado se establecerá en sólo ejecutar la aplicación de v2 de sistemas de salón de Skype. 
  
1. Tablet PC debe estar conectado a una fuente de alimentación. Iníciela cuando esté completamente apagada. Si es necesario, presione y mantener al presionar el botón de encendido hasta que se desactiva la tableta.
    
2. Conecte el disco de instalación de USB en Tablet PC.
    
3. Presione y mantenga el volumen hacia abajo (-) situado en el equipo Tablet PC. 
    
4. Presione y suelte el botón de encendido en el equipo Tablet PC.
    
5. Cuando se inicie la instalación de Windows, suelte el botón de reducción de volumen (-).
    
6. El sistema se cerrará una vez finalizada la instalación.
    
Después de que se apague el sistema, es seguro quitar el disco de instalación de USB. En este momento, puede colocar Tablet PC en el muelle y vincular los periféricos necesarios para la sala de reuniones. Consulte las instrucciones del fabricante.
  
 
### <a name="selecting-a-language-in-creators-update"></a>Selección de un idioma en la actualización del creador

En la actualización del creador, necesitará utilizar la secuencia de comandos ApplyCurrentRegionAndLanguage.ps1 en escenarios donde selección del idioma implícita no proporciona al usuario con el idioma de la aplicación real que desean (por ejemplo, desean que la aplicación para que surjan en francés, pero es próximamente en inglés).
  
> [!NOTE]
> Las instrucciones siguientes sólo funcionan para los dispositivos creados con Update del creador de Windows. No podrá usar estas instrucciones sistemas heredados/en-mercado que no hayan sido renovados correctamente para el nuevo sistema de aprovisionamiento, pero también no debe verse afectado desde el problema inicial que requiere esta intervención manual (aniversario Edition le permiten elegir su idioma de la aplicación explícitamente como parte del programa de instalación). 
  
### <a name="to-apply-your-desired-language"></a>Para aplicar el idioma deseado

1. Cambiar al modo de administrador.
    
2. Seleccione el menú Inicio.
    
3. Seleccione el icono de engranaje para iniciar la aplicación de **configuración** .
    
4. Seleccione **tiempo &amp; idioma**.
    
5. Seleccione **región &amp; idioma**.
    
6. Seleccione **Agregar un idioma**.
    
7. Seleccione el idioma que desea agregar.
    
8. Seleccione el idioma que acaba de agregar a la lista de "Idiomas".
    
9. Seleccione **establecer como predeterminado**.
    
10. Para los idiomas que desea quitar:
    
    a. Seleccione el idioma que desea quitar.
    
    b. Seleccione **Quitar**.
    
11. Inicie un símbolo del sistema con privilegios elevados.
    
12. Ejecute el siguiente comando: 
    
    PowerShell - executionpolicy sin restricciones c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    
13. Reinicie el sistema.
    
El idioma que desee ahora se aplica al dispositivo v2 de sistemas de salón de Skype.
## <a name="initial-set-up-of-the-console"></a>Configuración inicial de la consola 
<a name="Initial"> </a>

Después de instalar Windows, la aplicación de sistemas de salón de Skype v2 entra en su proceso de instalación inicial cuando se inicia siguiente o si se ha seleccionado la opción Reboot.
  
1. Aparece la pantalla Cuenta de usuario. Introduzca la dirección de inicio de sesión de Skype (con el formato usuario@dominio) de la cuenta de la sala que se va a utilizar con el dispositivo.
    
2. Introduzca la contraseña de la cuenta de la sala e introdúzcala una vez más para confirmarla.
    
3. Bajo "Configuración de dominio", establecer el FQDN para el Skype para Business Server. Si el Skype para el dominio SIP empresarial es diferente del dominio de Exchange del usuario, escriba el dominio de Exchange en este campo.
    
4. Haga clic en **Siguiente**.
    
5. Seleccione los dispositivos indicados en la pantalla de las características y haga clic en **siguiente**. De manera predeterminada, la opción Pantalla compartida automática está activada y Ocultar nombres de las reuniones está desactivada. Los dispositivos que se deben seleccionar son:
    
   - Micrófono para conferencias: el micrófono predeterminado de esta sala de conferencias.
    
   - Altavoz para conferencias: el altavoz predeterminado para las conferencias.  
    
   - Altavoz predeterminado: el altavoz que se usa para el audio de la transmisión por HDMI.
    
    Cada elemento tiene un menú desplegable en el que puede hacer selecciones. Deberá realizar una selección para cada dispositivo.
    
6. Haga clic en **Finalizar**.
    
La aplicación debe iniciar inmediatamente el inicio de sesión en Skype para Business Server 2015 con las credenciales especificadas anteriormente y también debe comenzar a sincronizar su calendario con Exchange utilizando las mismas credenciales. Para obtener información detallada sobre el uso de la aplicación, consulte la [Ayuda de sistemas de salón de Skype versión 2](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Sistemas de salón de Skype v2 se basa en la presencia de hardware de consola certificadas (el Logitech SmartDock). No se iniciará incluso una imagen creada correctamente que contiene la aplicación v2 de sistemas de salón de Skype cargada en un Surface Pro 4 o Surface Pro pasadas de un documento el procedimiento de instalación inicial, a menos que se detecta el hardware de la consola. 
  
> [!NOTE]
> Es posible que algunos usuarios que no sean de habla inglesa deban conectar un teclado físico a la consola durante la configuración inicial en caso de que los símbolos no se admitan en el teclado táctil. 
  
### <a name="install-a-private-ca-certificate-on-the-tablet-device"></a>Instalar un certificado de entidad de certificación privado en el dispositivo de tableta
<a name="Certs"> </a>

El dispositivo de v2 de sistemas de salón de Skype debe confiar en los certificados usados por el Skype para servidores empresariales y de Exchange a que se conecta. Para O365, este proceso se realiza automáticamente, puesto que los servidores utilizan entidades de certificación públicas y Windows 10 confía en ellas automáticamente. En un caso donde la entidad emisora de certificados es privada, por ejemplo, una implementación local con Active Directory y la entidad emisora de certificados de Windows, puede agregar el certificado en el dispositivo de v2 de sistemas de salón de Skype en un par de maneras:
  
- Puede unir el dispositivo a Active Directory y este agregará automáticamente los certificados necesarios, dado que la entidad de certificación los publica para Active Directory (opción de implementación normal).
    
- Puede instalar el certificado manualmente después del proceso de creación de imágenes. Antes de hacerlo, deberá completar la [Configuración inicial de la consola](console.md#Initial).  
    
### <a name="to-manually-install-the-certificate"></a>Para instalar manualmente el certificado 

1. Descargue el certificado de la entidad de certificación en su equipo y guárdelo en "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Colocar la superficie de 4 en modo de administrador (consulte [administración de modo y el dispositivo de administración](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).
    
3. Ejecute el siguiente comando:
    
  ```
  certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
  ```

### <a name="join-an-active-directory-domain-optional"></a>Unión al dominio de Active Directory (opcional)
<a name="Certs"> </a>

Puede participar en los dispositivos de sistemas de salón de Skype v2 a su dominio. Dispositivos de sistemas de salón de Skype v2 deben ubicarse en una unidad organizativa independiente desde estaciones de trabajo de sus PC debido a que muchas de las directivas de estación de trabajo no son compatibles con sistemas de salas de Skype v2. Un ejemplo común son las directivas de cumplimiento de contraseña que se impiden que se inicie automáticamente sistemas de salón de Skype v2. Para obtener información acerca de la administración de configuraciones de GPO, consulte [administrar sistemas de salón de Skype v2](../../manage/skype-room-systems-v2/room-systems-v2-operations.md). 
  
### <a name="to-join-skype-room-system-v2-to-a-domain"></a>Para unir Sistemas de salas de Skype v2 a un dominio

1. Inicio de sesión en la consola de la administración de cuenta (consulte [administración de modo y el dispositivo de administración](../../manage/skype-room-systems-v2/room-systems-v2-operations.md#AdminMode)).
    
2. Inicie un símbolo de sistema de PowerShell con privilegios elevados.
    
3. Introduzca el siguiente comando en PowerShell:
    
  ```
  Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
  ```

Por ejemplo, si su nombre de dominio completo es redmond.corp.microsoft.com y desea que los dispositivos de v2 de sistemas de salón de Skype para estar en un "v2 de sistemas de las salas de Skype" unidad organizativa que es un elemento secundario de una unidad organizativa "recursos", el comando será:
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Skype_Room_System,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si desea cambiar el nombre del equipo al unir a un dominio, use la marca - NewName seguida por el nombre del equipo nuevo.
  
## <a name="skype-room-systems-v2-deployment-checklist"></a>Lista de comprobación para la implementación de Sistemas de salas de Skype v2
<a name="Checklist"> </a>

Para realizar una comprobación final y asegurarse de que el dispositivo de consola y todos sus periféricos están totalmente configurados, utilice la siguiente lista de comprobación:
  
**Configuración de la aplicación**

|||
|:-----|:-----|
|☐  <br/> |El número de teléfono y el nombre de cuenta de la sala (si RTC está habilitado) se muestran correctamente en la parte superior derecha de la pantalla de la consola.  <br/> |
|☐  <br/> |El nombre del equipo con Windows está correctamente configurado (muy útil para la administración remota).  <br/> |
|☐  <br/> |La contraseña de la cuenta de administrador está configurada y comprobada.  <br/> |
|☐  <br/> |Se han aplicado todos los 4 Surface Pro o actualizaciones del sistema Surface Pro  <br/> |
   
**Periféricos de audio y vídeo**

|||
|:-----|:-----|
|☐  <br/> |La versión de firmware del periférico de cámara es correcta (si corresponde).  <br/> |
|☐  <br/> |Cámara funcional y colocado de manera óptima  <br/> |
|☐  <br/> |Configuración del dispositivo de reproducción predeterminado y del dispositivo de comunicaciones predeterminado para la reproducción establecida en el periférico de audio correspondiente.  <br/> |
|☐  <br/> |Configuración del dispositivo de comunicaciones predeterminado para la grabación establecida en el periférico de audio correspondiente.  <br/> |
|☐  <br/> |La versión de firmware del periférico de audio es correcta (si corresponde).  <br/> |
|☐  <br/> |El dispositivo de entrada de audio funciona y está posicionado correctamente.  <br/> |
|☐  <br/> |El dispositivo de salida de audio funciona y está posicionado correctamente.  <br/> |
   
**Muelle**

|||
|:-----|:-----|
|☐  <br/> |Los cables están protegidos y no están apretados.  <br/> |
|☐  <br/> |La transmisión de audio a través de HDMI funciona.  <br/> |
|☐  <br/> |La transmisión de vídeo a través de HDMI funciona.  <br/> |
|☐  <br/> |La base puede girar sin obstáculos.  <br/> |
|☐  <br/> |El brillo de la pantalla es el adecuado para el entorno.  <br/> |
   
## <a name="see-also"></a>Vea también
<a name="Checklist"> </a>

[Planeación de la sala de Skype v2 de sistemas](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[Implementación de salón de Skype v2 de sistemas](room-systems-v2.md)
  
[Configurar una consola de v2 de sistemas de salón de Skype](console.md)
  
[Administración de salón de Skype v2 de sistemas](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)