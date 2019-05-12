---
title: Configurar una consola de salas de equipos de Microsoft
ms.author: v-lanac
author: lanachin
ms.reviewer: Travis-Snoozy
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: En este artículo se describe cómo configurar la consola de salas de equipos de Microsoft y sus periféricos.
ms.openlocfilehash: 644006b3fe5a26af6c32830902ec138f953464c8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33916569"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurar una consola de salas de equipos de Microsoft

En este artículo se describe cómo configurar la consola de salas de equipos de Microsoft y sus periféricos.
  
Sólo debe realizar estos pasos si la es necesario Microsoft Teams o Skype para cuentas empresariales y de Exchange ya se han creado y probado tal como se describe en [Implementar Microsoft los equipos locales](room-systems-v2.md). Necesitará el hardware y software descritos en [requisitos de salas de equipos de Microsoft](requirements.md). Este tema incluye las secciones siguientes:
  
- [Preparar los medios de instalación](console.md#Prep_Media)
- [Instalar un certificado de entidad de certificación privado en la consola](console.md#Certs)
- [Instalar Windows 10 y la aplicación de consola de salas de equipos de Microsoft](console.md#Reimage)
- [Configuración inicial de la consola](console.md#Initial)
- [Lista de comprobación de implementación de salas de equipos de Microsoft](console.md#Checklist)

> [!NOTE]
> Salones de los equipos de Microsoft sólo funciona en un Microsoft Teams o Skype configuradas correctamente para el entorno empresarial donde las cuentas de dispositivos estén configuradas correctamente, tal como se describe en [Implementar Microsoft los equipos locales](room-systems-v2.md).
  
## <a name="prepare-the-installation-media"></a>Preparar los medios de instalación
<a name="Prep_Media"> </a>

Instalación de la aplicación de consola de salas de equipos de Microsoft requiere un dispositivo de almacenamiento USB con al menos 32GB de capacidad. No debe haber ningún otro archivo en el dispositivo; se perderán todos los archivos existentes en el almacenamiento USB.
  
> [!NOTE]
> Error al crear los discos de instalación de salas de equipos de Microsoft según estas instrucciones probablemente tendrá como resultado un comportamiento inesperado.

> [!NOTE]
> El proceso siguiente es para la creación de medios de instalación de dispositivos de imagen nuevos salones de los equipos de Microsoft. Dispositivos existentes, de forma predeterminada, se actualizan automáticamente desde el almacén de Windows y Windows Update.
  
1. Descargar el [script CreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Ejecute el script CreateSrsMedia.ps1 desde un símbolo de sistema con privilegios elevados en un equipo con Windows 10.
3. Siga las instrucciones de la secuencia de comandos para crear un disco de instalación de Microsoft los equipos salones USB.


> [!TIP]
> Cada vez que se inicia la secuencia de comandos CreateSrsMedia.ps1, la salida de pantalla incluirá el nombre de un archivo de registro o la transcripción de la sesión. Si hay problemas con la ejecución de la secuencia de comandos, asegúrese de tener una copia de ese transcripción disponible al solicitar soporte técnico. 

La secuencia de comandos CreateSrsMedia.ps1 automatiza las tareas siguientes:

1. Descargue al instalador MSI más reciente para salas de equipos de Microsoft.
2. Determinar la compilación de Windows que el usuario debe suministrar. Las versiones más recientes pueden o no ser probadas y compatibles para su uso con dispositivos de salas de equipos de Microsoft.
3. Descargar componentes auxiliares necesarios.
4. Ensamblar los componentes necesarios en los medios de instalación.

Se requiere una versión específica de Windows 10, y esta versión sólo está disponible para los clientes de licencias por volumen.  Puede obtener una copia desde el [Centro de servicio de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/).

Cuando termine, quitar el disco USB de su equipo y continúe con la [aplicación de consola de instalar Windows 10 y las salas de los equipos de Microsoft](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar Windows 10 y la aplicación de consola de salas de equipos de Microsoft
<a name="Reimage"> </a>

Debe aplicar el medio de instalación que se ha creado. El dispositivo de destino se ejecutará como un dispositivo y el usuario predeterminado se establecerá en sólo ejecutar la aplicación de consola de salas de equipos de Microsoft.

1. Si el dispositivo de destino se instalará en un muelle (por ejemplo, un Surface Pro), desconectar desde el muelle.

2. Asegúrese de que el dispositivo de destino no está conectado a la red.

3. Asegúrese de que el dispositivo de destino está conectado a la alimentación de CA.

4. Conecte el disco de instalación USB en el dispositivo de destino.

5. Inicie desde el disco de instalación USB. Consulte las instrucciones del fabricante. Si el dispositivo de destino es un Surface Pro, siga estos pasos para que arranque en el disco de instalación USB:

    a. Presione y mantenga el volumen hacia abajo botón (-).

    b. Presione y suelte el botón de encendido.

    c. Cuando se inicie la instalación de Windows, suelte el botón de reducción de volumen (-).

8. El sistema se cerrará una vez finalizada la instalación.
    
Después de que se apague el sistema, es seguro quitar el disco de instalación USB. En este momento, puede colocar el dispositivo de destino en su muelle (si se usa un producto de acoplamiento), adjunta los periféricos necesarios para la sala de reuniones y se conectan a la red. Consulte las instrucciones del fabricante.
  
### <a name="selecting-a-language"></a>Selección de un idioma 

En la actualización del creador, necesitará utilizar la secuencia de comandos ApplyCurrentRegionAndLanguage.ps1 en escenarios donde selección del idioma implícita no proporciona al usuario con el idioma de la aplicación real que desean (por ejemplo, desean que la aplicación de consola para que surjan en francés, pero se explica más adelante en inglés).
  
> [!NOTE]
> Las instrucciones siguientes sólo funcionan para consolas creadas mediante la actualización del creador de Windows. No podrá usar estas instrucciones sistemas heredados/en-mercado que no se ha configurado el uso de medios con el nuevo sistema de aprovisionamiento, pero también no debe verse afectado desde el problema inicial que requiere esta intervención manual (aniversario Edition le permiten elegir su idioma de la aplicación explícitamente como parte del programa de instalación).
  
### <a name="to-apply-your-desired-language"></a>Para aplicar el idioma deseado

1. Cambie al modo de administrador.
    
2. Seleccione el menú Inicio.
    
3. Seleccione el icono de engranaje para iniciar la aplicación **Configuración**.
    
4. Seleccione **tiempo &amp; idioma**.
    
5. Seleccione **región &amp; idioma**.
    
6. Seleccione **Agregar un idioma**.
    
7. Seleccione el idioma que desea agregar.
    
8. Seleccione el idioma que acaba de agregar a la lista de "Idiomas".
    
9. Haga clic en **Establecer como predeterminado**.
    
10. Si desea eliminar algún idioma:
    
    a. Seleccione el idioma que desea quitar.
    
    b. Seleccione **Quitar**.
    
11. Inicie un símbolo de sistema con privilegios elevados.
    
12. Ejecute el siguiente comando: 
    ```
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Reinicie el sistema.
    
El idioma deseado ahora se aplica a la consola de salas de equipos de Microsoft.
## <a name="initial-set-up-of-the-console"></a>Configuración inicial de la consola
<a name="Initial"> </a>

Después de instalar Windows, la aplicación de consola de salas de equipos de Microsoft entra en su proceso de instalación inicial cuando se inicia siguiente o si se ha seleccionado la opción Reboot.
  
1. Aparece la pantalla Cuenta de usuario. Escriba la Skype inicio de sesión de dirección (en formato user@domain) de la cuenta de sala para usarse con la consola.
    
2. Introduzca la contraseña de la cuenta de la sala e introdúzcala una vez más para confirmarla.
    
3. Bajo "Configuración de dominio", establecer el FQDN para el Skype para Business Server. Si el Skype para el dominio SIP empresarial es diferente del dominio de Exchange del usuario, escriba el dominio de Exchange en este campo.
    
4. Haga clic en **Siguiente**.
    
5. Seleccione los dispositivos indicados en la pantalla de las características y haga clic en **siguiente**. De manera predeterminada, la opción Pantalla compartida automática está activada y Ocultar nombres de las reuniones está desactivada. Los dispositivos que se deben seleccionar son:
    
   - Micrófono para conferencias: el micrófono predeterminado de esta sala de conferencias.
    
   - Altavoz para conferencias: el altavoz predeterminado para las conferencias.  
    
   - Altavoz predeterminado: el altavoz que se usa para el audio de la transmisión por HDMI.
    
     Cada elemento tiene un menú desplegable en el que puede hacer selecciones. Deberá realizar una selección para cada dispositivo.
    
6. Haga clic en **Finalizar**.
    
La aplicación de consola de salas de equipos de Microsoft debe iniciar inmediatamente el inicio de sesión en Skype para Business Server con las credenciales especificadas anteriormente y también debe comenzar a sincronizar su calendario con Exchange utilizando las mismas credenciales. Para obtener información detallada sobre el uso de la aplicación de consola, consulte la [Ayuda de salas de equipos de Microsoft](https://support.office.com/en-US/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Salones de los equipos de Microsoft se basa en la presencia de hardware de la consola certificados. Incluso una imagen creada correctamente que contiene la aplicación de consola de salas de equipos de Microsoft no se iniciará pasadas de un documento el procedimiento de instalación inicial, a menos que se detecta el hardware de la consola. Para las soluciones Surface Pro en función, debe estar conectado el Surface Pro a su hardware de acoplamiento que lo acompaña para pasar esta comprobación.
  
> [!NOTE]
> Algunos usuarios de idiomas distintos del inglés pueden necesitar un teclado físico conectado a la consola durante la instalación inicial en caso de que no se admiten los símbolos en el teclado táctil.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instalar un certificado de entidad de certificación privado en la consola
<a name="Certs"> </a>

Debe confiar en los certificados utilizados por los servidores a que se conecta la consola de salas de equipos de Microsoft. Para O365, este proceso se realiza automáticamente, puesto que los servidores utilizan entidades de certificación públicas y Windows 10 confía en ellas automáticamente. En un caso donde la entidad emisora de certificados es privada, por ejemplo, una implementación local con Active Directory y la entidad emisora de certificados de Windows, puede agregar el certificado a la consola de salas de equipos de Microsoft en un par de maneras:
  
- Puede unirse a la consola a Active Directory y que agregará automáticamente los certificados necesarios, dado la entidad emisora de certificados se publica en Active Directory (opción de implementación normal).
    
- Puede instalar el certificado manualmente después del proceso de creación de imágenes. Antes de hacerlo, debe completar la [configuración inicial de la consola](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Para instalar manualmente el certificado 

1. Descargue el certificado de la entidad de certificación en su equipo y guárdelo en "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloque la consola en modo de administrador (consulte [administración de modo y el dispositivo de administración](room-systems-v2-operations.md#AdminMode)).
    
3. Ejecute el siguiente comando:
    
   ```
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Unirse a un dominio de Active Directory (opcional)
<a name="Certs"> </a>

Puede unirse a consolas de salas de equipos de Microsoft a su dominio. Consolas de salas de equipos de Microsoft deben ubicarse en una unidad organizativa independiente desde estaciones de trabajo de sus PC porque muchas de las directivas de estación de trabajo no son compatibles con Microsoft los equipos locales. Un ejemplo común son las directivas de cumplimiento de contraseña que se impiden que se inicie automáticamente salones de los equipos de Microsoft. Para obtener información acerca de la administración de configuraciones de GPO, consulte [Manage Rooms de los equipos de Microsoft](room-systems-v2-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para unirse a salones de los equipos de Microsoft a un dominio

1. Inicio de sesión en la consola de la administración de cuenta (consulte [administración de modo y el dispositivo de administración](room-systems-v2-operations.md#AdminMode)).
    
2. Inicie un símbolo de sistema de PowerShell con privilegios elevados.
    
3. Introduzca el siguiente comando en PowerShell:
    
   ```
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Por ejemplo, si su nombre de dominio completo es redmond.corp.microsoft.com y desea que las consolas de salas de equipos de Microsoft para estar en una unidad organizativa "Salas de equipos de Microsoft" que es un elemento secundario de una unidad organizativa "recursos", el comando será:
  
```
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si desea cambiar el nombre del equipo al unir a un dominio, use la marca - NewName seguida por el nombre del equipo nuevo.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Lista de comprobación de implementación de salas de equipos de Microsoft
<a name="Checklist"> </a>

Utilizar la lista de comprobación siguiente mientras se hace una comprobación final que se han configurado totalmente la consola y todas sus periféricos:
  
**Configuración de la aplicación**

|||
|:-----|:-----|
|☐  <br/> |El número de teléfono y el nombre de cuenta de la sala (si RTC está habilitado) se muestran correctamente en la parte superior derecha de la pantalla de la consola.  <br/> |
|☐  <br/> |El nombre del equipo con Windows está correctamente configurado (muy útil para la administración remota).  <br/> |
|☐  <br/> |La contraseña de la cuenta de administrador está configurada y comprobada.  <br/> |
|☐  <br/> |Se han aplicado todas las actualizaciones de firmware  <br/> |
   
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
   
**Base**

|||
|:-----|:-----|
|☐  <br/> |Los cables están protegidos y no están apretados.  <br/> |
|☐  <br/> |La transmisión de audio a través de HDMI funciona.  <br/> |
|☐  <br/> |La transmisión de vídeo a través de HDMI funciona.  <br/> |
|☐  <br/> |La base puede girar sin obstáculos.  <br/> |
|☐  <br/> |El brillo de la pantalla es el adecuado para el entorno.  <br/> |
   
## <a name="see-also"></a>Vea también
<a name="Checklist"> </a>

[Plan para salas de equipos de Microsoft](skype-room-systems-v2-0.md)
  
[Implementación de salas de equipos de Microsoft](room-systems-v2.md)
  
[Configurar una consola de salas de equipos de Microsoft](console.md)
  
[Administrar Salas de Microsoft Teams](skype-room-systems-v2.md)
