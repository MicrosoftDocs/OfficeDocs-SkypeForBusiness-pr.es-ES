---
title: Configurar una consola de sala de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: En este artículo se describe cómo configurar la consola de Salas de Microsoft Teams y sus periféricos.
ms.openlocfilehash: 7a36ed93f370c0aeb302da246b223732383719fb
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662065"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurar una consola de sala de Microsoft Teams

En este artículo se describe cómo configurar la consola de Salas de Microsoft Teams y sus periféricos.
  
Solo debe realizar estos pasos si las cuentas necesarias de Microsoft Teams o Skype Empresarial y Exchange ya se han creado y probado como se describe en Implementar salas [de Microsoft Teams.](rooms-deploy.md) Necesitará el hardware y el software que se describen en los [requisitos de salas de Microsoft Teams.](requirements.md) Este tema incluye las secciones siguientes:
  
- [Preparar los medios de instalación](console.md#Prep_Media)
- [Instalar un certificado de entidad de certificación privado en la consola](console.md#Certs)
- [Instalar Windows 10 y la aplicación de consola salas de Microsoft Teams](console.md#Reimage)
- [Configuración inicial de la consola](console.md#Initial)
- [Lista de comprobación de implementación de salas de Microsoft Teams](console.md#Checklist)

> [!NOTE]
> Los salas de Microsoft Teams solo funcionarán en un entorno de Microsoft Teams o Skype Empresarial que esté configurado correctamente y que las cuentas de dispositivo estén configuradas correctamente como se describe en Implementar salas [de Microsoft Teams.](rooms-deploy.md)
  
## <a name="prepare-the-installation-media"></a>Preparar los medios de instalación
<a name="Prep_Media"> </a>

La instalación de la aplicación de consola De Microsoft Teams Rooms requiere un dispositivo de almacenamiento USB con al menos 32 GB de capacidad. No debería haber ningún otro archivo en el dispositivo; los archivos existentes en el almacenamiento USB se perderán.
  
> [!NOTE]
> Si no se crea el medio de instalación de salas de Microsoft Teams según estas instrucciones, es probable que se deba a un comportamiento inesperado.

> [!NOTE]
> El proceso siguiente es crear medios de instalación para crear imágenes de nuevos dispositivos de Salas de Microsoft Teams. Los dispositivos existentes, de forma predeterminada, se actualizan automáticamente desde Windows Update y la Tienda Windows.

> [!IMPORTANT]
> El equipo con Windows 10 usado para crear los medios de instalación de salas de Microsoft Teams debe estar en la misma versión de Windows o en una versión posterior que el medio de instalación de destino.
  
1. Descargue el [CreateSrsMedia.ps1 script.](https://go.microsoft.com/fwlink/?linkid=867842)
2. Ejecute el script CreateSrsMedia.ps1 desde un símbolo de sistema con privilegios elevados en un equipo con Windows 10.
3. Siga las instrucciones del script para crear un disco de instalación USB de Microsoft Teams Rooms.


> [!TIP]
> Cada vez que CreateSrsMedia.ps1 script, el resultado de la pantalla incluirá el nombre de un archivo de registro o transcripción de la sesión. Si hay problemas al ejecutar el script, asegúrese de que tiene una copia de la transcripción disponible al solicitar soporte técnico. 

El CreateSrsMedia.ps1 script automatiza las siguientes tareas:

1. Descargue el instalador MSI más reciente para Salas de Microsoft Teams.
2. Determine la compilación de Windows que debe proporcionar el usuario. Las versiones más recientes pueden o no probarse y ser compatibles con su uso con dispositivos de Microsoft Teams Rooms.
3. Descargue los componentes de soporte necesarios.
4. Ensamble los componentes necesarios en el medio de instalación.

Se requiere una versión específica de Windows 10 y esta versión solo está disponible para los clientes de licencias por volumen.  Puede obtener una copia en el Centro [de servicios de licencias por volumen.](https://www.microsoft.com/Licensing/servicecenter/)

Cuando termine, quite el disco USB de su equipo y continúe con la instalación [de Windows 10](console.md#Reimage)y la aplicación de consola de Salas de Microsoft Teams.

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar Windows 10 y la aplicación de consola salas de Microsoft Teams
<a name="Reimage"> </a>

Ahora debe aplicar los medios de configuración que ha creado. El dispositivo de destino se ejecutará como dispositivo y el usuario predeterminado se configurará para que solo ejecute la aplicación de consola de salas de Microsoft Teams.

1. Si el dispositivo de destino se instalará en una base (por ejemplo, un Surface Pro), desconéctelo de la base.

2. Asegúrese de que el dispositivo de destino no está conectado a la red.

3. Asegúrese de que el dispositivo de destino está conectado a alimentación de CA.

4. Conecta el disco de instalación USB en el dispositivo de destino.

5. Inicia en el disco de instalación USB. Consulte las instrucciones del fabricante. Si el dispositivo de destino es un Surface Pro, siga estos pasos para iniciar en el disco de instalación USB:

    a. Mantén presionado el botón de bajar volumen (-).

    b. Presiona y suelta el botón de inicio/apagado.

    c. Cuando se inicie la instalación de Windows, suelte el botón de reducción de volumen (-).

8. El sistema se cerrará cuando se complete la instalación.
    
Una vez que el sistema se haya apagado, es seguro quitar el disco de instalación USB. En este punto, puede colocar el dispositivo de destino en su base (si usa un producto basado en dock), conectar los periféricos necesarios para la sala de reuniones y conectarse a la red. Consulte las instrucciones del fabricante.

> [!NOTE]
> Las actualizaciones de software para salas de Microsoft Teams se descargan automáticamente desde Microsoft Store para Empresas. Consulte [los requisitos previos](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) de Microsoft Store para Empresas y Educación para comprobar que la consola de la sala pueda tener acceso a la tienda y actualizarse automáticamente.  

### <a name="selecting-a-language"></a>Seleccionar un idioma 

En Creator's Update, tendrá que usar el script ApplyCurrentRegionAndLanguage.ps1 en escenarios donde la selección de idioma implícito no proporciona al usuario el idioma real de la aplicación que desea (por ejemplo, desea que la aplicación de consola se descuelga en francés, pero se mostrará en inglés).
  
> [!NOTE]
> Las siguientes instrucciones funcionan solo para las consolas creadas con Windows Creator's Update. Los sistemas heredados o en el mercado que no se hayan configurado mediante medios con el nuevo sistema de aprovisionamiento no podrán usar estas instrucciones, pero tampoco deberían sufrir el problema inicial que requiere esta intervención manual (Anniversary Edition te permite elegir el idioma de la aplicación explícitamente como parte de la configuración).
  
### <a name="to-apply-your-desired-language"></a>Para aplicar el idioma deseado

1. Cambie al modo de administrador.
    
2. Seleccione el menú Inicio.
    
3. Seleccione el icono de engranaje para iniciar la aplicación **Configuración**.
    
4. Seleccione **Idioma de &amp; hora.**
    
5. Seleccione **Idioma de la &amp; región.**
    
6. Seleccione **Agregar un idioma**.
    
7. Seleccione el idioma que desea agregar.
    
8. Seleccione el idioma que acaba de agregar a la lista "Idiomas".
    
9. Haga clic en **Establecer como predeterminado**.
    
10. Si desea eliminar algún idioma:
    
    a. Seleccione el idioma que desea quitar.
    
    b. Seleccione **Quitar**.
    
11. Inicie un símbolo de sistema con privilegios elevados.
    
12. Ejecute el siguiente comando: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
13. Reinicie el sistema.
    
El idioma deseado se aplica ahora a la consola de Salas de Microsoft Teams.
## <a name="initial-set-up-of-the-console"></a>Configuración inicial de la consola
<a name="Initial"> </a>

Después de instalar Windows, la aplicación de consola de Salas de Microsoft Teams pasará al proceso de configuración inicial cuando se inicia a continuación o si se ha elegido la opción /reboot.
  
1. Aparece la pantalla Cuenta de usuario. Escribe la dirección de inicio de sesión de Skype (user@domain formato) de la cuenta de la sala que se usará con la consola.
    
2. Introduzca la contraseña de la cuenta de la sala e introdúzcala una vez más para confirmarla.
    
3. En "Configurar dominio", establezca el FQDN para Skype Empresarial Server. Si el dominio SIP de Skype Empresarial es diferente del dominio de Exchange del usuario, introduzca el dominio de Exchange en este campo.
    
4. Haga clic en **Siguiente**.
    
5. Seleccione los dispositivos indicados en la pantalla Características y haga clic en **Siguiente.** De manera predeterminada, la opción Pantalla compartida automática está activada y Ocultar nombres de las reuniones está desactivada. Los dispositivos que se deben seleccionar son:
    
   - Micrófono para conferencias: el micrófono predeterminado de esta sala de conferencias.
    
   - Altavoz para conferencias: el altavoz predeterminado para las conferencias.  
    
   - Altavoz predeterminado: el altavoz que se usa para el audio de la transmisión por HDMI.
    
     Cada elemento tiene un menú desplegable en el que puede hacer selecciones. Deberá realizar una selección para cada dispositivo.
    
6. Haga clic en **Finalizar**.
    
La aplicación de consola de salas de Microsoft Teams debería iniciar inmediatamente el inicio de sesión en Skype Empresarial Server con las credenciales especificadas anteriormente y, además, debería empezar a sincronizar su calendario con Exchange con esas mismas credenciales. Para obtener más información sobre el uso de la aplicación de consola, consulte la [ayuda de Salas de Microsoft Teams.](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)
  
> [!IMPORTANT]
> Los salas de Microsoft Teams dependen de la presencia de hardware certificado de la consola. Incluso una imagen creada correctamente que contenga la aplicación de consola de salas de Microsoft Teams no se inicia después del procedimiento de configuración inicial a menos que se detecte el hardware de la consola. Para las soluciones basadas en Surface Pro, Surface Pro debe estar conectado al hardware de la base que acompaña para pasar esta comprobación.
  
> [!NOTE]
> Es posible que algunos usuarios que no estén en inglés necesiten un teclado físico conectado a la consola durante la configuración inicial en caso de que los símbolos no sean compatibles con el teclado táctil.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instalar un certificado de entidad de certificación privado en la consola
<a name="Certs"> </a>

La consola de salas de Microsoft Teams necesita confiar en los certificados usados por los servidores a los que se conecta. Para O365, este proceso se realiza automáticamente, puesto que los servidores utilizan entidades de certificación públicas y Windows 10 confía en ellas automáticamente. Si la entidad emisora de certificados es privada, por ejemplo, una implementación local con Active Directory y Windows Certificate Authority, puede agregar el certificado a la consola de salas de Microsoft Teams de dos maneras:
  
- Puede unirse a la consola a Active Directory y esto agregará automáticamente los certificados necesarios que la entidad emisora de certificados publique en Active Directory (opción de implementación normal).
    
- Puede instalar el certificado manualmente después del proceso de creación de imágenes. Antes de hacerlo, debes completar la [configuración inicial de la consola.](console.md#Initial)
    
### <a name="to-manually-install-the-certificate"></a>Para instalar manualmente el certificado 

1. Descargue el certificado de la entidad de certificación en su equipo y guárdelo en "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloque la consola en modo de administrador (consulte [el modo de administración y la administración de dispositivos).](rooms-operations.md#AdminMode)
    
3. Ejecute el siguiente comando:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Unirse a un dominio de Active Directory (opcional)
<a name="Certs"> </a>

Puede unir las consolas de salas de Microsoft Teams a su dominio. Las consolas de Salas de Microsoft Teams deben colocarse en una unidad organizativa independiente de las estaciones de trabajo de su equipo, ya que muchas directivas de estaciones de trabajo no son compatibles con Salas de Microsoft Teams. Un ejemplo común son las directivas de aplicación de contraseñas que impedirán que Microsoft Teams Rooms se inicie automáticamente. Para obtener información sobre la administración de la configuración de GPO, consulte Administrar [salas de Microsoft Teams.](rooms-operations.md)
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para unirse a salas de Microsoft Teams en un dominio

1. Inicia sesión en la consola desde la cuenta de administrador (consulta [el modo de administración y la administración de dispositivos).](rooms-operations.md#AdminMode)
    
2. Inicie un símbolo de sistema de PowerShell con privilegios elevados.
    
3. Introduzca el siguiente comando en PowerShell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Por ejemplo, si su dominio completo es redmond.corp.microsoft.com y desea que las consolas de sus salas de Microsoft Teams se encontrarán en una UO de "Salas de Microsoft Teams" secundaria de una UO de "Recursos", el comando será:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si desea cambiar el nombre del equipo al unirse a un dominio, use la marca -NewName seguida del nombre nuevo del equipo.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Lista de comprobación de implementación de salas de Microsoft Teams
<a name="Checklist"> </a>

Use la siguiente lista de comprobación mientras se hace una comprobación final de que la consola y todos sus periféricos están totalmente configurados:
  
**Configuración de la aplicación**

|||
|:-----|:-----|
|☐  <br/> |El número de teléfono y el nombre de cuenta de la sala (si RTC está habilitado) se muestran correctamente en la parte superior derecha de la pantalla de la consola.  <br/> |
|☐  <br/> |El nombre del equipo con Windows está correctamente configurado (muy útil para la administración remota).  <br/> |
|☐  <br/> |La contraseña de la cuenta de administrador está configurada y comprobada.  <br/> |
|☐  <br/> |Se han aplicado todas las actualizaciones de firmware  <br/> |
   
**Periféricos de audio/vídeo**

|||
|:-----|:-----|
|☐  <br/> |La versión de firmware del periférico de cámara es correcta (si corresponde).  <br/> |
|☐  <br/> |La cámara funciona y se coloca de forma óptima  <br/> |
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
   
## <a name="see-also"></a>Consulte también
<a name="Checklist"> </a>

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)
