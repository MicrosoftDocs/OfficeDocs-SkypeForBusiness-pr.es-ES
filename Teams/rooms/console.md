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
description: En este artículo se describe cómo configurar y configurar la consola de salas de Microsoft Teams y sus periféricos.
ms.openlocfilehash: 7a36ed93f370c0aeb302da246b223732383719fb
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662065"
---
# <a name="configure-a-microsoft-teams-rooms-console"></a>Configurar una consola de sala de Microsoft Teams

En este artículo se describe cómo configurar la consola de salas de Microsoft Teams y sus periféricos.
  
Solo debe realizar estos pasos si ya se han creado y probado las cuentas de Microsoft Teams o Skype empresarial y Exchange, tal como se describe en [implementar salas de Microsoft Teams](rooms-deploy.md). Necesitará el hardware y el software descritos en [los requisitos de salas de Microsoft Teams](requirements.md). Este tema incluye las secciones siguientes:
  
- [Preparar los medios de instalación](console.md#Prep_Media)
- [Instalar un certificado de una entidad emisora privada en la consola](console.md#Certs)
- [Instalar Windows 10 y la aplicación Microsoft Teams Room Console](console.md#Reimage)
- [Configuración inicial de la consola](console.md#Initial)
- [Lista de comprobación de implementación de salas de Microsoft Teams](console.md#Checklist)

> [!NOTE]
> Las salas de Microsoft Teams solo funcionarán en un entorno de Microsoft Teams o Skype empresarial configurado correctamente, en el que las cuentas de dispositivos están configuradas correctamente, como se describe en [implementar salas de Microsoft Teams](rooms-deploy.md).
  
## <a name="prepare-the-installation-media"></a>Preparar los medios de instalación
<a name="Prep_Media"> </a>

La instalación de la aplicación de la consola de Microsoft Team Rooms requiere un dispositivo de almacenamiento USB con un mínimo de 32 GB de capacidad. No debe haber otros archivos en el dispositivo; los archivos existentes en el almacenamiento USB se perderán.
  
> [!NOTE]
> Si no se crean los medios de instalación de Microsoft Teams Rooms según estas instrucciones, es posible que se produzcan comportamientos inesperados.

> [!NOTE]
> El proceso que se muestra a continuación es para crear medios de instalación para crear nuevos dispositivos de salas de Microsoft Teams. Los dispositivos existentes, de forma predeterminada, se actualizan automáticamente desde Windows Update y la tienda Windows.

> [!IMPORTANT]
> El equipo con Windows 10 usado para crear el medio de instalación de Microsoft Team Rooms debe estar en la misma versión de Windows o en una posterior, como el medio de instalación de destino.
  
1. Descargue el [ script deCreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Ejecute el script CreateSrsMedia.ps1 desde un símbolo de sistema con privilegios elevados en un equipo con Windows 10.
3. Siga las instrucciones de la secuencia de comandos para crear un disco de instalación de cámaras USB de Microsoft Teams.


> [!TIP]
> Cada vez que se inicie el script de CreateSrsMedia.ps1, el resultado de la pantalla incluirá el nombre de un archivo de registro o transcripción de la sesión. Si hay problemas para ejecutar el script, asegúrese de tener una copia de esa transcripción disponible cuando solicite asistencia. 

El script de CreateSrsMedia.ps1 automatiza las siguientes tareas:

1. Descargue el programa de instalación MSI más reciente para salas de Microsoft Teams.
2. Determine la compilación de Windows que el usuario debe proporcionar. Las versiones publicadas más recientes pueden ser o no probadas y admitidas para su uso con dispositivos de salas de Microsoft Teams.
3. Descargar componentes auxiliares necesarios.
4. Ensamble los componentes necesarios en los medios de instalación.

Se necesita una versión específica de Windows 10 y esta versión solo está disponible para los clientes de licencias por volumen.  Puede obtener una copia en el [centro de servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/).

Cuando termine, quite el disco USB de su equipo y continúe para [instalar Windows 10 y la aplicación Microsoft Teams Rooms Console](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar Windows 10 y la aplicación Microsoft Teams Room Console
<a name="Reimage"> </a>

Ahora debe aplicar los medios de configuración que ha creado. El dispositivo de destino se ejecutará como un dispositivo y el usuario predeterminado se configurará para que solo ejecute la aplicación Microsoft Teams Rooms Console.

1. Si el dispositivo de destino se va a instalar en un muelle (p. ej., una Surface Pro), desconéctelo del Dock.

2. Asegúrate de que el dispositivo de destino no esté conectado a la red.

3. Asegúrate de que el dispositivo de destino esté conectado a la alimentación de CA.

4. Conecte el disco de instalación USB en el dispositivo de destino.

5. Inicie el disco de instalación de USB. Consulte las instrucciones del fabricante. Si el dispositivo de destino es Surface Pro, siga estos pasos para arrancar en el disco de instalación de USB:

    a. Pulsa y continúa con el botón bajar de volumen (-).

    b. Presione y suelte el botón Power (encendido).

    c. Cuando se inicie la instalación de Windows, suelte el botón de reducción de volumen (-).

8. El sistema se cerrará cuando se complete la instalación.
    
Una vez que el sistema se ha cerrado, es seguro quitar el disco de instalación de USB. En este punto, puede colocar el dispositivo de destino en su muelle (si usa un producto basado en el muelle), adjuntar los periféricos necesarios para la sala de reuniones y conectarse a la red. Consulte las instrucciones del fabricante.

> [!NOTE]
> Las actualizaciones de software para Microsoft Team Rooms se descargan automáticamente de Microsoft Store para empresas. Consulte los [requisitos previos de Microsoft Store para empresas y educación](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) para comprobar que la consola de la sala podrá acceder a la tienda y a la actualización automática.  

### <a name="selecting-a-language"></a>Selección de un idioma 

En la actualización de su creador, tendrá que usar el script de ApplyCurrentRegionAndLanguage.ps1 en escenarios en los que la selección de idioma implícito no proporciona al usuario el lenguaje de aplicaciones que quieren (por ejemplo, desea que la aplicación de consola aparezca en francés, pero está llegando en inglés).
  
> [!NOTE]
> Las siguientes instrucciones solo funcionan con las consolas creadas con la actualización de Windows Creator. Los sistemas heredados o en el mercado que no se hayan configurado con medios en el nuevo sistema de aprovisionamiento no podrán usar estas instrucciones, pero tampoco deben sufrir el problema inicial que requiere esta intervención manual (la edición de aniversario le permite elegir el idioma de la aplicación de forma explícita como parte de la configuración).
  
### <a name="to-apply-your-desired-language"></a>Para aplicar el idioma deseado

1. Cambie al modo de administrador.
    
2. Seleccione el menú Inicio.
    
3. Seleccione el icono de engranaje para iniciar la aplicación **Configuración**.
    
4. Seleccione **&amp; idioma de tiempo**.
    
5. Seleccione **el &amp; idioma** de la región.
    
6. Seleccione **Agregar un idioma**.
    
7. Seleccione el idioma que desea agregar.
    
8. Seleccione el idioma que acaba de agregar a la lista "idiomas".
    
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
    
El idioma deseado se aplica ahora a la consola de salones de Microsoft Teams.
## <a name="initial-set-up-of-the-console"></a>Configuración inicial de la consola
<a name="Initial"> </a>

Una vez instalado Windows, la aplicación Microsoft Teams Rooms Console pasará a su proceso de configuración inicial cuando se inicie a continuación o si se eligió la opción/Reboot.
  
1. Aparece la pantalla Cuenta de usuario. Escribe la dirección de inicio de sesión de Skype (en user@domain formato) de la cuenta de la sala para usarla con la consola.
    
2. Introduzca la contraseña de la cuenta de la sala e introdúzcala una vez más para confirmarla.
    
3. En "Configurar dominio", establezca el FQDN de Skype empresarial Server. Si el dominio SIP de Skype empresarial es diferente del dominio de Exchange del usuario, escriba el dominio de Exchange en este campo.
    
4. Haga clic en **Siguiente**.
    
5. Seleccione los dispositivos indicados en la pantalla características y haga clic en **siguiente**. De manera predeterminada, la opción Pantalla compartida automática está activada y Ocultar nombres de las reuniones está desactivada. Los dispositivos que se deben seleccionar son:
    
   - Micrófono para conferencias: el micrófono predeterminado de esta sala de conferencias.
    
   - Altavoz para conferencias: el altavoz predeterminado para las conferencias.  
    
   - Altavoz predeterminado: el altavoz que se usa para el audio de la transmisión por HDMI.
    
     Cada elemento tiene un menú desplegable en el que puede hacer selecciones. Deberá realizar una selección para cada dispositivo.
    
6. Haga clic en **Finalizar**.
    
La aplicación Microsoft Team Rooms Console debe empezar a iniciar sesión en Skype empresarial Server inmediatamente con las credenciales especificadas anteriormente, y también debe empezar a sincronizar su calendario con Exchange con las mismas credenciales. Para obtener información sobre el uso de la aplicación de consola, consulte la [ayuda de Microsoft Teams Rooms](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Las salas de Microsoft Teams se basan en la presencia de un hardware de consola certificado. Incluso una imagen creada correctamente que contenga la aplicación salas de Microsoft Teams en la consola, no arrancará más allá del procedimiento de configuración inicial, a menos que se detecte el hardware de la consola. Para las soluciones basadas en Surface Pro, la Surface Pro debe estar conectada a su hardware de acoplamiento adjunto para pasar esta comprobación.
  
> [!NOTE]
> Es posible que algunos usuarios de idiomas no ingleses necesiten un teclado físico conectado a la consola durante la configuración inicial, en el caso de que los símbolos no se admitan en el teclado táctil.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instalar un certificado de una entidad emisora privada en la consola
<a name="Certs"> </a>

La consola de salones de Microsoft Teams necesita confiar en los certificados que usan los servidores a los que se conecta. Para O365, este proceso se realiza automáticamente, puesto que los servidores utilizan entidades de certificación públicas y Windows 10 confía en ellas automáticamente. En el caso de que la entidad emisora de certificados sea privada, por ejemplo, una implementación local con Active Directory y la entidad emisora de certificados de Windows, puede Agregar el certificado a la consola de salas de Microsoft Teams de dos maneras:
  
- Puede unirse a la consola a Active Directory y se agregarán automáticamente los certificados necesarios dados que la entidad emisora de certificados se publique en Active Directory (opción de implementación normal).
    
- Puede instalar el certificado manualmente después del proceso de creación de imágenes. Antes de hacerlo, debe completar [la configuración inicial de la consola](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Para instalar manualmente el certificado 

1. Descargue el certificado de la entidad de certificación en su equipo y guárdelo en "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloque la consola en el modo de administración (consulte [modo de administración y administración de dispositivos](rooms-operations.md#AdminMode)).
    
3. Ejecute el siguiente comando:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Unirse a un dominio de Active Directory (opcional)
<a name="Certs"> </a>

Puede unirse a las consolas de salas de Microsoft Teams en su dominio. Las consolas de salas de Microsoft Teams deben colocarse en una OU independiente de las estaciones de trabajo de PC porque muchas directivas de estación de trabajo no son compatibles con las salas de Microsoft Teams. Un ejemplo común son las directivas de aplicación de contraseñas que evitarán que las salas de Microsoft Teams se inicien automáticamente. Para obtener información sobre la administración de la configuración de GPO, consulte [administrar salas de Microsoft Teams](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para unirse a salas de Microsoft Teams a un dominio

1. Inicie sesión en la consola desde la cuenta de administrador (consulte [modo de administración y administración de dispositivos](rooms-operations.md#AdminMode)).
    
2. Inicie un símbolo de sistema de PowerShell con privilegios elevados.
    
3. Introduzca el siguiente comando en PowerShell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Por ejemplo, si su dominio completo es redmond.corp.microsoft.com y desea que las consolas de salas de Microsoft Teams estén en una OU "salas de Microsoft Teams" que sea un elemento secundario de una unidad organizativa "recursos", el comando será:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si desea cambiar el nombre del equipo cuando se une a un dominio, use la bandera-NewName seguida del nombre nuevo del equipo.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Lista de comprobación de implementación de salas de Microsoft Teams
<a name="Checklist"> </a>

Use la siguiente lista de comprobación para realizar una verificación final de que la consola y todos sus periféricos estén totalmente configurados:
  
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
|☐  <br/> |Funciones de cámara y posición óptima  <br/> |
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
