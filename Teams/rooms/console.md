---
title: Crear una Salas de Microsoft Teams imagen
ms.author: czawideh
author: cazawideh
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
ms.custom: seo-marvel-apr2020
ms.assetid: dae1bfb6-7262-4030-bf53-dc3b3fe971ea
description: En este artículo se describe cómo configurar y configurar la Salas de Microsoft Teams y sus periféricos.
ms.openlocfilehash: c13a247f2ce9d7fee7571f7f3a202310b2ce8b41
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514725"
---
# <a name="build-a-microsoft-teams-rooms-image"></a>Crear una Salas de Microsoft Teams imagen

En este artículo se describe cómo crear una imagen Salas de Microsoft Teams para la implementación masiva de Salas de Teams.

> [!NOTE]
> Los pasos siguientes solo deben usarse al crear una imagen basada en [WIM](/windows-hardware/manufacture/desktop/capture-and-apply-an-image) para la implementación masiva. Si está recuperando dispositivos individuales, póngase en contacto con el Fabricante de equipos originales (OEM) para obtener soporte técnico.

Solo debe realizar estos pasos si las cuentas Microsoft Teams o Skype Empresarial y Exchange ya se han creado y probado como se describe en Implementar [Salas de Microsoft Teams](rooms-deploy.md). Necesitará el hardware y el software descritos en [Salas de Microsoft Teams requisitos.](requirements.md) Este tema incluye las secciones siguientes:
  
- [Preparar los medios de instalación](console.md#Prep_Media)
- [Instalar un certificado de CA privado en la consola](console.md#Certs)
- [Instalar Windows 10 y la aplicación Salas de Microsoft Teams consola](console.md#Reimage)
- [Configuración inicial de la consola](console.md#Initial)
- [Salas de Microsoft Teams lista de comprobación de implementación](console.md#Checklist)

## <a name="prepare-the-installation-media"></a>Preparar los medios de instalación
<a name="Prep_Media"> </a>

Instalar la Salas de Microsoft Teams de consola requiere un dispositivo de almacenamiento USB con al menos 32 GB de capacidad. No debería haber otros archivos en el dispositivo; los archivos existentes en el almacenamiento USB se perderán.
  
> [!NOTE]
> Si no se crea el Salas de Microsoft Teams de instalación de acuerdo con estas instrucciones, es probable que se deba a un comportamiento inesperado.

> [!NOTE]
> El proceso siguiente es para crear medios de instalación para crear imágenes de Salas de Microsoft Teams dispositivos. Los dispositivos existentes, de forma predeterminada, se actualizan automáticamente desde Windows Actualización y el Windows Store.

> [!IMPORTANT]
> El Windows 10 usado para crear el Salas de Microsoft Teams de instalación debe estar en la misma versión o posterior de Windows que el medio de instalación de destino.
  
1. Descargue el [CreateSrsMedia.ps1 script](https://go.microsoft.com/fwlink/?linkid=867842).
2. Ejecute el script CreateSrsMedia.ps1 desde un símbolo de sistema con privilegios elevados en un equipo con Windows 10.
3. Siga las instrucciones del script para crear un Salas de Microsoft Teams de configuración USB.


> [!TIP]
> Cada vez que CreateSrsMedia.ps1 script, el resultado de la pantalla incluirá el nombre de un archivo de registro o una transcripción para la sesión. Si hay problemas con la ejecución del script, asegúrese de tener una copia de esa transcripción disponible al solicitar soporte técnico. 

El CreateSrsMedia.ps1 script automatiza las siguientes tareas:

1. Descargue el instalador MSI más reciente para Salas de Microsoft Teams.
2. Determine la compilación de Windows que el usuario debe proporcionar. Las versiones publicadas más recientemente pueden o no probarse y ser compatibles para su uso con Salas de Microsoft Teams dispositivos.
3. Descargue los componentes de soporte necesarios.
4. Ensamble los componentes necesarios en el medio de instalación.

> [!NOTE]
Se requiere una versión específica de Windows 10 y esta versión solo está disponible para los clientes de licencias por volumen.  Puede obtener una copia del Centro de servicios de licencias [por volumen](https://www.microsoft.com/Licensing/servicecenter/).

Cuando termine, quite el disco USB del equipo y continúe con [Instalar Windows 10 la aplicación de Salas de Microsoft Teams consola](console.md#Reimage).

    
## <a name="install-windows-10-and-the-microsoft-teams-rooms-console-app"></a>Instalar Windows 10 y la aplicación Salas de Microsoft Teams consola
<a name="Reimage"> </a>

Ahora debe aplicar los medios de configuración que ha creado. El dispositivo de destino se ejecutará como un dispositivo y el usuario predeterminado se establecerá para que solo ejecute la Salas de Microsoft Teams aplicación.

1. Si el dispositivo de destino se instalará en un dock (por ejemplo, un Surface Pro), desconéctelo del dock.

2. Asegúrese de que el dispositivo de destino no está conectado a la red.

3. Asegúrese de que el dispositivo de destino está conectado a la alimentación de CA.

4. Conecta el disco de configuración USB al dispositivo de destino.

5. Inicie en el disco de configuración USB. Consulte las instrucciones del fabricante. Si el dispositivo de destino es un Surface Pro, siga estos pasos para iniciar en el disco de configuración USB:

    a. Mantén presionado el botón de bajar el volumen (-).

    b. Presione y suelte el botón de encendido.

    c. Cuando se inicie la instalación de Windows, suelte el botón de reducción de volumen (-).

8. El sistema se cerrará una vez completada la instalación.
    
Después de que el sistema se haya apagado, es seguro quitar el disco de configuración USB. En este punto, puede colocar el dispositivo de destino en su dock (si usa un producto basado en dock), adjuntar los periféricos necesarios para la sala de reuniones y conectarse a la red. Consulte las instrucciones del fabricante.

> [!NOTE]
> Las actualizaciones de software Salas de Microsoft Teams se descargan automáticamente desde el Microsoft Store para Empresas. Consulte [Requisitos previos para Microsoft Store para Empresas y Educación](/microsoft-store/prerequisites-microsoft-store-for-business) para comprobar que la consola de sala podrá acceder a la tienda y actualizarse automáticamente.  

### <a name="selecting-a-language"></a>Seleccionar un idioma 

En Creator's Update, tendrá que usar el script de ApplyCurrentRegionAndLanguage.ps1 en escenarios en los que la selección implícita de idioma no proporciona al usuario el idioma real de la aplicación que quiere (por ejemplo, quiere que la aplicación de consola suba en francés, pero está en inglés).
  
> [!NOTE]
> Las siguientes instrucciones solo funcionan para consolas creadas con Windows Actualización del creador (Windows 10 20H1) o posterior.
  
### <a name="to-apply-your-desired-language"></a>Para aplicar el idioma deseado

1. Cambie al modo de administrador.
    
2. Seleccione el menú Inicio.
    
3. Seleccione el icono de engranaje para iniciar la aplicación **Configuración**.
    
4. Seleccione **Idioma de &amp; hora**.
    
5. Seleccione **el idioma**.
    
6. Seleccione **Agregar un idioma**.
    
7. Seleccione el idioma que desea agregar.
    
8. Instalar características de idioma.
    
9. No active Establecer como mi Windows idioma para mostrar.
    
10. Seleccione **Instalar**.
    
11. Seleccione el idioma que acaba de agregar a la lista "Idiomas".
    
12. Establecer como predeterminado: flecha arriba para establecer el valor predeterminado

13. Si desea eliminar algún idioma:
    
    a. Seleccione el idioma que desea quitar.
    
    b. Seleccione Quitar.

14. Inicie un símbolo de sistema con privilegios elevados.

15. Ejecute el siguiente comando: 
    ```PowerShell
    powershell -executionpolicy unrestricted c:\Rigel\x64\scripts\provisioning\scriptlaunch.ps1 ApplyCurrentRegionAndLanguage.ps1
    ```
    
16. Reinicie el sistema.
    
El idioma que desee ahora se aplica a la Salas de Microsoft Teams consola.
## <a name="initial-set-up-of-the-console"></a>Configuración inicial de la consola
<a name="Initial"> </a>

Después Windows instalación, la aplicación Salas de Microsoft Teams pasará a su proceso de configuración inicial.
  
1. Aparece la pantalla Cuenta de usuario. Escriba la dirección de inicio de sesión de Exchange recurso de Microsoft (en user@domain formato) de la cuenta de salón que se usará con la consola.
    
2. Introduzca la contraseña de la cuenta de la sala e introdúzcala una vez más para confirmarla.
   
3. Seleccione el modo de reunión admitido: solo Microsoft Teams, solo Skype Empresarial o una de las dos opciones de modo mixto. Si es necesario, habilite autenticación moderna.

4. Seleccione **Siguiente**.
    
5. Si usa Skype Empresarial y si el dominio SIP de Skype Empresarial es diferente del dominio Exchange del usuario, establezca el FQDN para el Skype Empresarial Server en la sección Avanzadas. Si no usa Skype Empresarial o el dominio SIP coincide con el Exchange, deje esta sección en blanco.
6. Seleccione **Siguiente**.
    
7. Seleccione **Finalizar**.
    
La Salas de Microsoft Teams debe iniciar sesión en Microsoft Teams o Skype Empresarial Server con las credenciales especificadas anteriormente y también debe empezar a sincronizar su calendario con Exchange con esas mismas credenciales. Para obtener más información sobre Salas de Teams, consulte la [Salas de Microsoft Teams ayuda](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2).
  
> [!IMPORTANT]
> Salas de Microsoft Teams depende de la presencia de hardware de consola certificado. Incluso una imagen creada correctamente que contenga Salas de Microsoft Teams aplicación de consola no se iniciará más allá del procedimiento de configuración inicial a menos que se detecte el hardware de la consola. Para Surface Pro soluciones basadas en, el Surface Pro debe estar conectado a su hardware de base adjunto para pasar esta comprobación.
  
> [!NOTE]
> Es posible que algunos usuarios que no estén en inglés necesiten un teclado físico conectado a la consola durante la configuración inicial en caso de que los símbolos no sean compatibles con el teclado táctil.
  
### <a name="install-a-private-ca-certificate-on-the-console"></a>Instalar un certificado de CA privado en la consola
<a name="Certs"> </a>
> [!NOTE]
> Lo siguiente solo se aplica si se conecta Salas de Teams a Skype Empresarial.

Salas de Microsoft Teams debe confiar en los certificados usados por los servidores a los que se conecta. En un caso en el que la entidad de certificación es privada, por ejemplo, una implementación local con Active Directory y la entidad de certificación de Windows, puede agregar el certificado a Salas de Microsoft Teams de varias maneras:
  
- Puede unirse a la consola a Active Directory y eso agregará automáticamente los certificados necesarios dado que la entidad de certificación se publica en Active Directory (opción de implementación normal).
    
- Puede instalar el certificado manualmente después del proceso de creación de imágenes. Antes de hacerlo, debe completar la [configuración inicial de la consola](console.md#Initial).
    
### <a name="to-manually-install-the-certificate"></a>Para instalar manualmente el certificado 

1. Descargue el certificado de la entidad de certificación en su equipo y guárdelo en "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer".
    
2. Coloque la consola en modo de administrador (consulte [Modo de administración y administración de dispositivos](rooms-operations.md#AdminMode)).
    
3. Ejecute el siguiente comando:
    
   ```PowerShell
   certutil -addstore -f -enterprise root "C:\Skype Room Systems\x64\Scripts\Provisioning\CAcertificate.cer"
   ```

### <a name="join-an-active-directory-domain-optional"></a>Unirse a un dominio de Active Directory (opcional)
<a name="Certs"> </a>

Puede unirse Salas de Microsoft Teams a su dominio. Salas de Microsoft Teams deben colocarse en una unidad organizativa independiente de las estaciones de trabajo del equipo porque muchas directivas de estaciones de trabajo no son compatibles con Salas de Microsoft Teams. Un ejemplo común es una directiva de aplicación de contraseñas que evitará Salas de Microsoft Teams iniciar automáticamente. Para obtener información sobre la administración de la configuración de GPO, consulte [Administrar Salas de Microsoft Teams](rooms-operations.md).
  
### <a name="to-join-microsoft-teams-rooms-to-a-domain"></a>Para unirse Salas de Microsoft Teams a un dominio

1. Inicie sesión en la consola desde la cuenta de administrador (consulte [Modo de administración y administración de dispositivos](rooms-operations.md#AdminMode)).
    
2. Inicie un símbolo de sistema de PowerShell con privilegios elevados.
    
3. Introduzca el siguiente comando en PowerShell:
    
   ```PowerShell
   Add-Computer -DomainName <Fully qualified domain> -OUPath "OU=<Child OU>, … ,OU=<Top level OU>,DC=<child domain>,…,DC=<top level domain>"
   ```

Por ejemplo, si su dominio completo está redmond.corp.microsoft.com y desea que las consolas de Salas de Microsoft Teams se en una unidad organizativa "Salas de Microsoft Teams" que sea un elemento secundario de una unidad organizativa "Recursos", el comando será:
  
```PowerShell
Add-Computer -DomainName redmond.corp.microsoft.com -OUPath "OU=Microsoft_Teams_Rooms,OU=Resources,DC=redmond,DC=corp,DC=microsoft,DC=com"
```

 Si desea cambiar el nombre del equipo al unirse a un dominio, use la marca -NewName seguida del nuevo nombre del equipo.
  
## <a name="microsoft-teams-rooms-deployment-checklist"></a>Salas de Microsoft Teams lista de comprobación de implementación
<a name="Checklist"> </a>

Use la siguiente lista de comprobación mientras hace una comprobación final de que la consola y todos sus periféricos están totalmente configurados:
  
**Configuración de la aplicación**

|Completado |Comprobar |
|:-----:|:-----|
|☐   |El nombre de la cuenta del salón y el teléfono # (si RTC habilitado) se muestran correctamente   |
|☐   |El nombre del equipo con Windows está correctamente configurado (muy útil para la administración remota).   |
|☐   |La contraseña de la cuenta de administrador está configurada y comprobada.   |
|☐   |Se han aplicado todas las actualizaciones de firmware   |
   
**Periféricos de audio y vídeo**

|Completado |Comprobar |
|:-----:|:-----|
|☐   |La versión de firmware del periférico de cámara es correcta (si corresponde).   |
|☐   |Cámara funcional y posicionada de forma óptima   |
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
|☐   |La consola puede girar libremente   |



   
## <a name="see-also"></a>Vea también
<a name="Checklist"> </a>

[Plan para Salas de Microsoft Teams](rooms-plan.md)
  
[Implementar Salas de Microsoft Teams](rooms-deploy.md)
  
[Configurar una consola de sala de Microsoft Teams](console.md)
  
[Administrar Salas de Microsoft Teams](rooms-manage.md)
