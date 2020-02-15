---
title: Preparar Active Directory para Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Resumen: Obtenga información sobre cómo preparar el dominio de Active Directory para una instalación de Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del centro de evaluación de Microsoft https://www.microsoft.com/evalcenter/evaluate-skype-for-business-serveren:.'
ms.openlocfilehash: 9a17ae327322b364935d0b965676d26fdce2cffb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018181"
---
# <a name="prepare-active-directory-for-skype-for-business-server"></a>Preparar Active Directory para Skype empresarial Server
 
**Resumen:** Obtenga información sobre cómo preparar el dominio de Active Directory para una instalación de Skype empresarial Server. Descargue una versión de prueba gratuita de Skype empresarial Server del [centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype empresarial Server funciona estrechamente con Active Directory. Debe preparar el dominio de Active Directory para que funcione con Skype empresarial Server. Este proceso se realiza en el Asistente para la implementación y solo se realiza una vez para el dominio. Esto se debe a que el proceso crea grupos y modifica el dominio, y solo debe hacerlo una vez. Puede realizar los pasos del 1 al 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden, y después de los pasos del 1 al 5, tal y como se describe en el diagrama. La preparación de Active Directory es el paso 4 de 8. Para obtener más información acerca de la planeación de Active Directory, consulte [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).
  
![diagrama de información general](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparar Active Directory

Skype empresarial Server está estrechamente integrado con los servicios de dominio de Active Directory (AD DS). Para poder instalar Skype empresarial Server por primera vez, Active Directory debe estar preparado. La sección del Asistente para la implementación titulada **preparar Active** Directory prepara el entorno de Active Directory para su uso con Skype empresarial Server.
  
> [!NOTE]
> Skype empresarial Server usa (AD DS) para realizar un seguimiento y comunicarse con todos los servidores de una topología. La mayoría de estos servidores deben unirse al dominio para que Skype empresarial Server pueda funcionar correctamente. Tenga en cuenta que los servidores como el servidor perimetral y el proxy inverso no deben estar Unidos a un dominio.
  
> [!IMPORTANT]
> El procedimiento de preparación de Active Directory solo debe ejecutarse una vez para cada dominio de la implementación. 
  
Vea los pasos del vídeo para **preparar Active**Directory:
  
> [!video https://www.microsoft.com/videoplayer/embed/RE1Ybuk]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Preparar Active Directory desde el Asistente para la implementación

1. Inicie sesión como un usuario con credenciales de administrador de esquema para el dominio de Active Directory.
    
2. Abra el Asistente para la implementación de Skype empresarial Server.
    
    > [!TIP]
    > Si desea revisar los archivos de registro que crea el Asistente para la implementación de Skype empresarial Server, puede encontrarlos en el equipo en el que se ejecutó el Asistente para la implementación en el directorio de usuarios del usuario de AD DS que ejecutó el paso. Por ejemplo, si el usuario ha iniciado sesión como administrador de dominio en el dominio contoso. local, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Haga clic en el vínculo **preparar Active** Directory.
    
4. **Paso 1: preparar el esquema**
    
    a. Revise la información de requisitos previos del paso 1 al que se puede obtener acceso haciendo clic en la lista desplegable en el título del paso 1.
    
    b. Haga clic en **Ejecutar** en el paso 1 para iniciar el Asistente para preparar el esquema.
    
    c. Tenga en cuenta que el procedimiento solo debe ejecutarse una vez por cada implementación y, a continuación, haga clic en **siguiente**.
    
    d. Una vez que se ha preparado el esquema, puede ver el registro si hace clic en **Ver registro**. 
    
    e. Haga clic en **Finalizar** para cerrar el Asistente para preparar el esquema y volver a los pasos de preparación de Active Directory.
    
5. **Paso 2: comprobar la replicación de la partición del esquema**
    
    a. Inicie sesión en el controlador de dominio del dominio.
    
    b. Abra el editor **ADSI** desde el menú desplegable **herramientas** en el **Administrador de servidores**.
    
    c. En el menú **Acción**, haga clic en **Conectar con**.
    
    d. En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, a continuación, haga clic en **Aceptar**.
    
    e. En el contenedor de esquema, busque **CN = MS-RTC-SIP-SchemaVersion**. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente. Si este objeto no existe o los valores de los atributos **rangeUpper** y **rangeLower** no son los especificados, el esquema no se modificó o no se ha replicado.
    
6. **Paso 3: preparar el bosque actual**
    
    a. Revise la información de requisitos previos del paso 3, al que se puede obtener acceso haciendo clic en el menú desplegable en el título del paso 3.
    
    b. Haga clic en **Ejecutar** en el paso 3 para iniciar el Asistente para preparar el bosque actual.
    
    c. Tenga en cuenta que el procedimiento solo debe ejecutarse una vez por cada implementación y, a continuación, haga clic en **siguiente**.
    
    d. Especifique el dominio donde se crearán los grupos universales. Si el servidor es parte del dominio, puede elegir **dominio local**y hacer clic en **siguiente**.
    
    e. Una vez preparado el bosque, puede ver el registro si hace clic en **Ver registro**. 
    
    f. Haga clic en **Finalizar** para cerrar el Asistente para preparar el bosque actual y volver a los pasos de preparación de Active Directory.
    
    g. Haga clic en **Shell de administración de Skype empresarial Server** en la página **aplicaciones** para iniciar PowerShell.
    
    h. Escriba el comando Get-CsAdForest y presione **entrar**.
    
    sigo. Si el resultado es **LC_FORESTSETTINGS_STATE_READY**, el bosque se ha preparado correctamente, tal como se muestra en la figura.
    
     ![Compruebe la replicación del bosque.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Paso 4: comprobar la replicación del catálogo global**
    
    a. En un controlador de dominio (preferiblemente en un sitio remoto desde otros controladores de dominio) del bosque en el que se ejecutó la preparación del bosque, abra  **Usuarios y equipos de Active Directory **.
    
    b. En **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.
    
    c. Haga clic en el contenedor **usuarios** en el panel izquierdo y busque el grupo universal **CsAdministrator** en el panel derecho. Si CsAdministrator (entre otros grupos universales nuevos que comienzan con CS) está presente, la replicación de Active Directory se ha realizado correctamente.
    
    d. Si los grupos todavía no están presentes, puede forzar la replicación o esperar 15 minutos y actualizar el panel derecho. Cuando los grupos están presentes, la replicación se ha completado.
    
8. **Paso 5: preparar el dominio actual**
    
    a. Revise la información de requisitos previos para el paso 5.
    
    b. Haga clic en **Ejecutar** en el paso 5 para iniciar el Asistente para preparar el dominio actual.
    
    c. Tenga en cuenta que el procedimiento solo debe ejecutarse una vez para cada dominio de la implementación y, a continuación, haga clic en **siguiente**.
    
    d. Una vez que se ha preparado el dominio, puede ver el registro al hacer clic en **Ver registro**. 
    
    e. Haga clic en **Finalizar** para cerrar el Asistente para preparar el dominio actual y volver a los pasos de preparación de Active Directory.
    
    Estos pasos deben completarse en todos los dominios en los que se encuentren objetos de Skype empresarial Server; de lo contrario, es posible que los servicios no se inicien. Esto incluye cualquier tipo de objeto de Active Directory, como usuarios, objetos de contacto, grupos administrativos o cualquier otro tipo de objeto. Puede usar Set-CsUserReplicatorConfiguration-ADDomainNamingContextList para agregar solo los dominios con objetos de Skype empresarial Server, si es necesario.
    
9. **Paso 6: comprobar la replicación en el dominio**
    
    a. Haga clic en **Shell de administración de Skype empresarial Server** en la página **aplicaciones** para iniciar PowerShell.
    
    b. Use el comando Get-CsAdDomain para comprobar la replicación dentro del dominio.
    
   ```powershell
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
   ```

    > [!NOTE]
    > Si no especifica el parámetro de dominio, el valor se configura con el dominio local. 
  
    Ejemplo de la ejecución del comando para el dominio contoso. local:
    
   ```powershell
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local
   ```

    > [!NOTE]
    > Mediante el uso del parámetro GlobalSettingsDomainController, puede indicar dónde se almacena la configuración global. Si la configuración se almacena en el contenedor del sistema (que es típica con las implementaciones de actualización que no tenían la configuración global migrada al contenedor de configuración), se define un controlador de dominio en la raíz del bosque de AD DS. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), deberá definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet presupone que la configuración se almacena en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory. 
  
    c. Si el resultado es **LC_DOMAINSETTINGS_STATE_READY**, el dominio se ha replicado correctamente.
    
10. **Paso 7: agregar usuarios para proporcionar acceso administrativo al panel de control de Skype empresarial Server**
    
    a. Inicie sesión como miembro del grupo Admins. del dominio o del grupo RTCUniversalServerAdmins.
    
    b. Abra **usuarios y equipos de Active**Directory, expanda el dominio, haga clic en el contenedor **usuarios** , haga clic con el botón secundario en CSAdministrator y elija **propiedades**.
    
    c. En **Propiedades de CSAdministrator**, haga clic en la pestaña **Miembros**.
    
    d. En la pestaña **Miembros**, haga clic en **Agregar**. En **Seleccionar usuarios, contactos, equipos, cuentas de servicio o grupos**, busque **Escribir los nombres de objeto para seleccionar**. Escriba el nombre o los nombres de usuario, o bien el nombre o los nombres de grupo que desee agregar al grupo CSAdministrators. Haga clic en **Aceptar**.
    
    e. En la pestaña **miembros** , confirme que están presentes los usuarios o grupos que ha seleccionado. Haga clic en **Aceptar**.
    
    > [!CAUTION]
    > El panel de control de Skype empresarial Server es una herramienta de control de acceso basada en roles. Pertenencia al grupo CsAdministrator da a un usuario que usa el control total del panel de control de Skype empresarial Server para todas las funciones de configuración disponibles. Hay otros roles disponibles diseñados para funciones específicas. Para obtener más información sobre los roles disponibles, consulte [Environmental Requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) o [Server Requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md). Tenga en cuenta que los usuarios no tienen que estar habilitados para Skype empresarial Server para poder ser miembros de los grupos de administración. 
  
    > [!CAUTION]
    > Para ayudar a mantener la seguridad y la integridad del control de acceso basado en roles, agregue usuarios a los grupos que definen qué rol realiza el usuario en la administración de la implementación de Skype empresarial Server. 
  
11. Cierre la sesión y, a continuación, vuelva a iniciar sesión en Windows para que el token de seguridad se actualice con el nuevo grupo de seguridad de Skype empresarial Server y, a continuación, vuelva a abrir el Asistente para la implementación.
    
12. Compruebe que ve una marca de verificación verde junto a **preparar Active** Directory para confirmar que se ha realizado correctamente, como se muestra en la figura.
    
     ![Se ha completado la preparación de Active Directory.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

## <a name="see-also"></a>Consulte también
 
[Servicios de dominio de Active Directory para Skype empresarial Server 2015](../../plan-your-deployment/security/active-directory-domain-services.md)
