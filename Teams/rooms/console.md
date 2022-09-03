---
title: Crear una imagen de Salas de Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: Travis-Snoozy
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: En este artículo se describe cómo configurar la consola de Salas de Microsoft Teams y sus periféricos.
ms.openlocfilehash: 40d49597ab3354eeaacc8d7c562917fbf653e727
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590177"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>Crear una imagen de Salas de Microsoft Teams

En este artículo se describe cómo crear una imagen de Salas de Microsoft Teams para la implementación masiva de Salas de Teams.

> [!NOTE]
> Los pasos siguientes solo deben usarse al crear una [imagen basada en WIM](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) para la implementación masiva. Si estás recuperando dispositivos individuales, ponte en contacto con el fabricante de equipos originales (OEM) para obtener soporte técnico.

Solo debe realizar estos pasos si ya se han creado y probado las cuentas necesarias de Microsoft Teams o de Skype Empresarial y Exchange, como se describe en [Implementar Salas de Microsoft Teams](rooms-deploy.md). Necesitarás el hardware y el software que se describen en [Salas de Microsoft Teams requisitos](requirements.md). Este tema incluye las secciones siguientes:
  
- [Preparar los medios de instalación](console.md#Prep_Media)
- [Instalar un certificado de CA privado en la consola](console.md#Certs)
- [Instalar Windows 10 y la aplicación de consola de Salas de Microsoft Teams](console.md#Reimage)
- [Configuración inicial de la consola](console.md#Initial)
- [Salas de Microsoft Teams lista de comprobación de implementación](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>Preparar los medios de instalación
<a name="Prep_Media"> </a>

La instalación de la aplicación de consola Salas de Microsoft Teams requiere un dispositivo de almacenamiento USB con al menos 32 GB de capacidad. No debería haber otros archivos en el dispositivo; se perderán todos los archivos existentes en el almacenamiento USB.
  
> [!NOTE]
> Si no se crean los medios de instalación Salas de Microsoft Teams de acuerdo con estas instrucciones, probablemente se producirá un comportamiento inesperado.

> [!NOTE]
> El siguiente proceso es para crear medios de instalación para crear imágenes de nuevos dispositivos Salas de Microsoft Teams. De forma predeterminada, los dispositivos existentes se actualizan automáticamente desde Windows Update y la Tienda Windows.

> [!IMPORTANT]
> El equipo Windows 10 que se usa para crear el Salas de Microsoft Teams medios de instalación debe estar en la misma versión o posterior de Windows que el medio de instalación de destino.
  
1. Descargue el [ script deCreateSrsMedia.ps1](https://go.microsoft.com/fwlink/?linkid=867842).
2. Ejecute el script CreateSrsMedia.ps1 desde un símbolo de sistema con privilegios elevados en un equipo con Windows 10.
3. Sigue las instrucciones del script para crear un Salas de Microsoft Teams disco de instalación USB.


> [!TIP]
> Cada vez que se inicie el script de CreateSrsMedia.ps1, la salida de pantalla incluirá el nombre de un archivo de registro o una transcripción de la sesión. Si hay problemas con la ejecución del script, asegúrese de tener una copia de esa transcripción disponible al solicitar soporte técnico. 

El script de CreateSrsMedia.ps1 automatiza las siguientes tareas:

1. Descargue el instalador msi más reciente para Salas de Microsoft Teams.
2. Determina la compilación de Windows que el usuario debe proporcionar. Las versiones más recientes pueden o no probarse y admitirse para su uso con Salas de Microsoft Teams dispositivos.
3. Descargue los componentes auxiliares necesarios.
4. Ensamble los componentes necesarios en los medios de instalación.

> [!NOTE]
Se requiere una versión específica de Windows 10 y esta versión solo está disponible para los clientes de licencias por volumen.  Puede obtener una copia del Centro de [servicios de licencias por volumen](https://www.microsoft.com/Licensing/servicecenter/).

Cuando termine, quite el disco USB del equipo y vaya a [Instalar Windows 10 y la aplicación de consola Salas de Microsoft Teams](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar Windows 10 y la aplicación de consola de Salas de Microsoft Teams
<a name="Reimage"> </a>

Ahora debe aplicar los medios de configuración que ha creado. El dispositivo de destino se ejecutará como un dispositivo y el usuario predeterminado solo podrá ejecutar la aplicación de Salas de Microsoft Teams.

1. Si el dispositivo de destino se instalará en una base (por ejemplo, una Surface Pro), desconéctalo de la base.

2. Asegúrate de que el dispositivo de destino no esté conectado a la red.

3. Asegúrate de que el dispositivo de destino esté conectado a la alimentación de CA.

4. Conecta el disco de configuración USB al dispositivo de destino.

5. Arranque en el disco de instalación usb. Consulte las instrucciones del fabricante. Si el dispositivo de destino es un Surface Pro, sigue estos pasos para arrancar en el disco de instalación USB:

    a. Mantén presionado el botón de bajar volumen (-).

    b. Presiona y suelta el botón de inicio/apagado.

    c. Cuando se inicie la instalación de Windows, suelte el botón de reducción de volumen (-).

8. El sistema se apagará una vez completada la instalación.
    
Una vez apagado el sistema, es seguro quitar el disco de instalación USB. En este punto, puede colocar el dispositivo de destino en su base (si usa un producto basado en la base), adjuntar los periféricos necesarios para la sala de reuniones y conectarse a la red. Consulte las instrucciones del fabricante.

> [!NOTE]
> Las actualizaciones de software para Salas de Microsoft Teams se descargan automáticamente desde el Microsoft Store para Empresas. Consulte [Requisitos previos para Microsoft Store para Empresas y Educación](/microsoft-store/prerequisites-microsoft-store-for-business) para comprobar que la consola de la sala podrá acceder a la tienda y la actualización automática.  

### <a name="selecting-a-language"></a>Seleccionar un idioma 

En Creator's Update, tendrás que usar el script de ApplyCurrentRegionAndLanguage.ps1 en escenarios en los que la selección implícita de idioma no proporciona al usuario el idioma de la aplicación real que quiere (por ejemplo, quiere que la aplicación de consola aparezca en francés, pero viene en inglés).
  
> [!NOTE]
> Las instrucciones siguientes solo funcionan para las consolas creadas con Windows Creators Update (Windows 10 20H1) o posterior.
  
### <a name="to-apply-your-desired-language"></a>Para aplicar el idioma deseado

1. Cambie al modo de administrador.
    
2. Seleccione el menú Inicio.
    
3. Seleccione el icono de engranaje para iniciar la aplicación **Configuración**.
    
4. Selecciona **Idioma de la hora&amp;**.
    
5. Seleccionar **idioma**.
    
6. Seleccione **Agregar un idioma**.
    
7. Seleccione el idioma que desea agregar.
    
8. Instalar características de idioma.
    
9. No active Establecer como idioma para mostrar de Windows.
    
10. Selecciona **Instalar**.
    
11. Selecciona el idioma que acabas de agregar a la lista "Idiomas".
    
12. Establecer como predeterminado: flecha subir para establecer como predeterminado

13. Si desea eliminar algún idioma:
    
    a. Seleccione el idioma que desea quitar.
    
    b. Seleccione Quitar.

14. Inicie un símbolo de sistema con privilegios elevados.

15. Ejecute el siguiente comando: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
16. Reinicie el sistema.
    
El idioma deseado ahora se aplica a la consola de Salas de Microsoft Teams.
## <a name="initial-set-up-of-the-console"></a>Configuración inicial de la consola
<a name="Initial"> </a>

Después de instalar Windows, la aplicación Salas de Microsoft Teams pasará a su proceso de instalación inicial.
  
1. Aparece la pantalla Cuenta de usuario. Escriba la dirección de inicio de sesión de la cuenta de recursos de Microsoft Exchange (en formato de user@domain) de la cuenta de sala que se usará con la consola.
    
2. Introduzca la contraseña de la cuenta de la sala e introdúzcala una vez más para confirmarla.
   
3. Seleccione el modo de reunión compatible: Solo Microsoft Teams, solo Skype Empresarial o una de las dos opciones de modo mixto. Si es necesario, habilite la autenticación moderna.

4. Seleccione **Siguiente**.
    
5. Si el uso de Skype Empresarial y si el Skype Empresarial dominio SIP es diferente del dominio de Exchange del usuario, establezca el FQDN para el Skype Empresarial Server en la sección Avanzadas. Si no usa Skype Empresarial o el dominio SIP coincide con el dominio de Exchange, deje esta sección en blanco.
6. Seleccione **Siguiente**.
    
7. Selecciona **Finalizar**.
    
La aplicación Salas de Microsoft Teams debe iniciar sesión en Microsoft Teams o Skype Empresarial Server con las credenciales especificadas anteriormente, y también debería iniciar la sincronización de su calendario con Exchange con esas mismas credenciales. Para obtener más información sobre el uso de Salas de Teams, consulte la [ayuda de Salas de Microsoft Teams](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Salas de Microsoft Teams se basa en la presencia de hardware de consola certificado. Incluso una imagen creada correctamente que contenga la aplicación de consola Salas de Microsoft Teams no arrancará más allá del procedimiento de configuración inicial, a menos que se detecte el hardware de la consola. Para obtener Surface Pro soluciones basadas en, el Surface Pro debe estar conectado a su hardware de la base de acoplamiento correspondiente para pasar esta comprobación. Para obtener más información sobre el hardware compatible, consulta [requisitos de Salas de Microsoft Teams](requirements.md).
  
> [!NOTE]
> Es posible que algunos usuarios que no sean del idioma inglés necesiten un teclado físico conectado a la consola durante la configuración inicial en caso de que los símbolos no sean compatibles con el teclado táctil.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instalar un certificado de CA privado en la consola
<a name="Certs"> </a>
> [!NOTE]
> Lo siguiente solo se aplica si se conecta Salas de Teams a Skype Empresarial.

Salas de Microsoft Teams debe confiar en los certificados usados por los servidores a los que se conecta. En un caso en el que la entidad emisora de certificados es privada, por ejemplo, una implementación local con Active Directory y la entidad emisora de certificados de Windows, puede agregar el certificado a Salas de Microsoft Teams de un par de formas:
  
- Puede unir la consola a Active Directory y esto agregará automáticamente los certificados necesarios, dado que la entidad emisora de certificados se publica en Active Directory (opción de implementación normal).
    
- Puede instalar el certificado manualmente después del proceso de creación de imágenes. Antes de hacerlo, debe completar [la configuración inicial de la consola](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Para instalar manualmente el certificado 

1. Descargue el certificado de la entidad de certificación en su equipo y guárdelo en "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloca la consola en modo de administración (consulta [modo de Administración y administración de dispositivos](rooms-operations.md#AdminMode)).
    
3. Ejecute el siguiente comando:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Unirse a un dominio de Active Directory (opcional)
<a name="Certs"> </a>

Puede unir Salas de Microsoft Teams a su dominio. Salas de Microsoft Teams deben colocarse en una unidad organizativa independiente de las estaciones de trabajo del equipo, ya que muchas directivas de estaciones de trabajo no son compatibles con Salas de Microsoft Teams. Un ejemplo común es una directiva de aplicación de contraseñas que impedirá que Salas de Microsoft Teams se inicie automáticamente. Para obtener información sobre la administración de la configuración de GPO, consulte [Administrar Salas de Microsoft Teams](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para unir Salas de Microsoft Teams a un dominio

1. Inicia sesión en la consola desde la cuenta de administrador (consulta [modo de Administración y administración de dispositivos](rooms-operations.md#AdminMode)).
    
2. Inicie un símbolo de sistema de PowerShell con privilegios elevados.
    
3. Introduzca el siguiente comando en PowerShell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, ... ,OU=<Top level OU>,DC=<child domain>,...,DC=<top level domain>"
   ```

Por ejemplo, si el dominio completo está redmond.corp.microsoft.com y quiere que las consolas de Salas de Microsoft Teams estén en una unidad organizativa "Salas de Microsoft Teams" que sea un elemento secundario de una unidad organizativa "Recursos", el comando será:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si desea cambiar el nombre del equipo al unirlo a un dominio, use la marca -NewName seguida del nuevo nombre del equipo.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Salas de Microsoft Teams lista de comprobación de implementación
<a name="Checklist"> </a>

Usa la siguiente lista de comprobación mientras realizas una comprobación final de que la consola y todos sus periféricos están completamente configurados:
  
**Configuración de la aplicación**

|Completado |Comprobar |
|:-----:|:-----|
|☐   |El nombre de la cuenta de sala y el número de teléfono (si RTC está habilitado) se muestran correctamente   |
|☐   |El nombre del equipo con Windows está correctamente configurado (muy útil para la administración remota).   |
|☐   |La contraseña de la cuenta de administrador está configurada y comprobada.   |
|☐   |Se han aplicado todas las actualizaciones de firmware   |
   
**Periféricos de audio y vídeo**

|Completado |Comprobar |
|:-----:|:-----|
|☐   |La versión de firmware del periférico de cámara es correcta (si corresponde).   |
|☐   |Cámara funcional y colocada de forma óptima   |
|☐   |Configuración del dispositivo de reproducción predeterminado y del dispositivo de comunicaciones predeterminado para la reproducción establecida en el periférico de audio correspondiente.   |
|☐   |Configuración del dispositivo de comunicaciones predeterminado para la grabación establecida en el periférico de audio correspondiente.   |
|☐   |La versión de firmware del periférico de audio es correcta (si corresponde).   |
|☐   |El dispositivo de entrada de audio funciona y está posicionado correctamente.   |
|☐   |El dispositivo de salida de audio funciona y está posicionado correctamente.   |

**Consola**

|Completado |Comprobar |
|:-----:|:-----|
|☐   |Los cables están protegidos y no están apretados.   |
|☐   |La transmisión de audio a través de HDMI funciona.   |
|☐   |La transmisión de vídeo a través de HDMI funciona.   |
|☐   |La consola puede deslizar el dedo libremente   |



   
## <a name="see-also"></a>Vea también
<a name="Checklist"> </a>

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)
