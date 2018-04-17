---
title: Preparar Active Directory para Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 985077a4-c8e1-4d5a-9fcf-fef41cf6d61d
description: 'Resumen: Conozca cómo preparar el dominio de Active Directory para la instalación de Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el centro de Evaluation de Microsoft en: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: a1344bab451bd9c4b46a0147bd2ffb1190dbe900
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="prepare-active-directory-for-skype-for-business-server-2015"></a>Preparar Active Directory para Skype Empresarial Server 2015
 
**Resumen:** Aprenda a preparar su dominio de Active Directory para la instalación de Skype para Business Server 2015. Descargue una prueba gratuita de Skype para Business Server 2015 desde el [Centro de evaluación de Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Skype para Business Server trabaja estrechamente con Active Directory. Debe preparar el dominio de Active Directory para trabajar con Skype para Business Server. Este proceso se lleva a cabo en el Asistente para implementación y se realiza sólo una vez para el dominio. Esto es porque el proceso crea grupos y modifica el dominio, y debe hacer que sólo una vez. Puede realizar los pasos 1 a 5 en cualquier orden. Sin embargo, debe realizar los pasos 6, 7 y 8 en orden y después los pasos del 1 al 5, tal como se indica en el diagrama. Preparación de Active Directory es el paso 4 de 8. Para obtener más información acerca de cómo planear Active Directory, consulte [los requisitos ambientales para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).
  
![diagrama de información general](../../media/2c52d307-7859-4009-9489-024b2e130bb3.png)
  
## <a name="prepare-active-directory"></a>Preparar Active Directory

Skype para Business Server 2015 está estrechamente integrado con los servicios de dominio de Active Directory (AD DS). Para poder instalar Skype para Business Server 2015 por primera vez, se debe preparar Active Directory. La sección del Asistente de implementación titulado **Preparar Active Directory** prepara el entorno de Active Directory para su uso con Skype para Business Server.
  
> [!NOTE]
> Skype para Business Server 2015 utiliza (AD DS) para realizar un seguimiento y comunicarse con todos los servidores en una topología. Cada servidor debe estar unido al dominio para que Skype para Business Server pueda funcionar correctamente. 
  
> [!IMPORTANT]
> Es necesario ejecutar el procedimiento de preparación de Active Directory solo una vez por cada dominio en la implementación. 
  
Vea los pasos del vídeo **Preparar Active Directory**:
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/272c856b-b3e0-4324-9635-42720c48b75a?autoplay=false]
  
### <a name="prepare-active-directory-from-the-deployment-wizard"></a>Preparar Active Directory desde el Asistente para la implementación

1. Inicie sesión como usuario con credenciales de administrador de esquema para el dominio de Active Directory.
    
2. Abre Skype para el Asistente para implementación de Business Server.
    
    > [!TIP]
    > Si desea revisar los archivos de registro creados por el Skype para el Asistente para implementación de Business Server, puede encontrarlas en el equipo donde se ejecuta el Asistente de implementación, en el directorio de usuarios del usuario de AD DS que se ejecutó el paso. Por ejemplo, si el usuario inició sesión como el administrador del dominio en el dominio, contoso.local, los archivos de registro se encuentran en: C:\Users\Administrator.Contoso\AppData\Local\Temp. 
  
3. Haga clic en el vínculo **Preparar Active Directory**.
    
4. **Paso 1: Preparar el esquema**
    
    a. Haga clic en el menú desplegable debajo del título del paso 1 y revise la información sobre los requisitos previos para este paso.
    
    b. Haga clic en **Ejecutar** en el paso 1 a fin de iniciar el asistente para preparar el esquema.
    
    c. Recuerde que el procedimiento solo tiene que ejecutarse una vez por cada implementación; luego, haga clic en **Siguiente**.
    
    d. Una vez que haya preparado el esquema, puede ver el registro al hacer clic en **Ver registro**. 
    
    e. Haga clic en **Finalizar** y así cerrar el asistente para la preparación del esquema y regresar a los pasos para preparar Active Directory.
    
5. **Paso 2: Comprobar la replicación de la partición de esquema**
    
    a. Inicie sesión en el controlador de dominio para el dominio.
    
    b. Abra **Editar ADSI** desde el menú desplegable **Herramientas** en **Administrador de servidores**.
    
    c. En el menú **Acción**, haga clic en **Conectar con**.
    
    d. En el cuadro de diálogo **Configuración de conexión**, en **Seleccione un contexto de nomenclatura conocido**, seleccione **Esquema** y, luego, haga clic en **Aceptar**.
    
    e. En el contenedor de esquema, busque **CN=ms-RTC-SIP-SchemaVersion**. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente. Si este objeto no existe o si el valor de los atributos **rangeUpper** y **rangeLower** es distinto de lo que se ha especificado, el esquema no se ha modificado o no se ha replicado.
    
6. **Paso 3: Preparar bosque actual**
    
    a. Haga clic en el menú desplegable debajo del título del paso 3 y revise la información sobre los requisitos previos para este paso.
    
    b. Haga clic en **Ejecutar** en el paso 3 a fin de iniciar el asistente para preparar el bosque actual.
    
    c. Recuerde que el procedimiento solo tiene que ejecutarse una vez por cada implementación; luego, haga clic en **Siguiente**.
    
    d. Especifique el dominio donde se crearán los grupos universales. Si el servidor es parte del dominio, puede seleccionar **Dominio local** y hacer clic en **Siguiente**.
    
    e. Una vez que haya preparado el bosque, puede ver el registro al hacer clic en **Ver registro**. 
    
    f. Haga clic en **Finalizar** y así cerrar el asistente para la preparación del bosque actual y regresar a los pasos para preparar Active Directory.
    
    g. Haga clic en **Skype para el Shell de administración de servidor empresarial** desde la página de **aplicaciones** para iniciar PowerShell.
    
    h. Escriba el comando Get-CsAdForest y presione **ENTRAR**.
    
    . Si el resultado es **LC_FORESTSETTINGS_STATE_READY**, el bosque correctamente se ha preparado, como se muestra en la figura.
    
     ![Verifique la replicación del bosque.](../../media/20835669-b8ff-445b-aa8d-51cce46a8b0e.png)
  
7. **Paso 4: Comprobar la replicación del catálogo global**
    
    a. En un controlador de dominio (preferentemente en un sitio remoto desde otros controladores de dominio) en el bosque donde se ejecutó la preparación del bosque, abra **Usuarios y equipos de Active Directory**.
    
    b. En **Usuarios y equipos de Active Directory**, expanda el nombre de dominio del bosque o un dominio secundario.
    
    c. Haga clic en el contenedor **Usuarios** del panel izquierdo y busque el grupo universal **CsAdministrator** en el panel derecho. Si CsAdministrator (entre los otros grupos universales nuevos que empiezan con Cs) está presente, la replicación de Active Directory se ha realizado correctamente.
    
    d. Si los grupos aún no están presentes, puede forzar la replicación o esperar 15 minutos y actualizar el panel derecho. Cuando los grupos están presentes, la replicación se ha completado.
    
8. **Paso 5: Preparar el dominio actual**
    
    a. Revise la información sobre los requisitos previos para el paso 5.
    
    b. Haga clic en **Ejecutar** en el paso 5 a fin de iniciar el asistente para preparar el dominio actual.
    
    c. Recuerde que el procedimiento solo tiene que ejecutarse una vez por cada dominio en la implementación; luego, haga clic en **Siguiente**.
    
    d. Una vez que haya preparado el dominio, puede ver el registro al hacer clic en **Ver registro**. 
    
    e. Haga clic en **Finalizar** y así cerrar el asistente para la preparación del dominio actual y regresar a los pasos para preparar Active Directory.
    
    Debe realizar estos pasos en cada dominio donde Skype para los objetos Business Server se encuentran, de lo contrario los servicios es posible que no se inicie. Dichos objetos incluyen todo tipo de objetos de Active Directory, como usuarios, objetos de contacto, grupos administrativos o todo otro tipo de objeto. Puede utilizar Set-CsUserReplicatorConfiguration - ADDomainNamingContextList para agregar sólo los dominios con Skype para objetos de servidor de la empresa, si es necesario.
    
9. **Paso 6: Comprobar la replicación en el dominio**
    
    a. Haga clic en **Skype para el Shell de administración de servidor empresarial** desde la página de **aplicaciones** para iniciar PowerShell.
    
    b. Utilice el comando Get-CsAdDomain para comprobar la replicación dentro del dominio.
    
   ```
   Get-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>]
 
   ```

    > [!NOTE]
    > Si no especifica el parámetro de dominio, el valor se configura con el dominio local. 
  
    Ejemplo de la ejecución del comando para el dominio contoso.local:
    
   ```
   Get-CsAdDomain -Domain contoso.local -GlobalSettingsDomainController dc.contoso.local

   ```

    > [!NOTE]
    > El uso del parámetro GlobalSettingsDomainController permite indicar dónde se guarda la configuración global. Si la configuración se guarda en el contenedor del sistema (habitual en implementaciones de actualización cuya configuración global no se ha migrado al contenedor de configuración), necesitará definir un controlador de dominio en la raíz del bosque de AD DS. Si la configuración global se encuentra en el contenedor de configuración (habitual en implementaciones nuevas o de actualización en las que la configuración se ha migrado al contenedor de configuración), necesitará definir cualquier controlador de dominio en el bosque. Si no especifica este parámetro, el cmdlet da por sentado que la configuración se guarda en el contenedor de configuración y hace referencia a cualquier controlador de dominio de Active Directory. 
  
    c. Si el resultado es **LC_DOMAINSETTINGS_STATE_READY**, el dominio se ha replicado correctamente.
    
10. **Paso 7: Agregar usuarios para proporcionar acceso administrativo a la Skype Business Server Control Panel**
    
    a. Inicie sesión como miembro del grupo Administradores del dominio o del grupo RTCUniversalServerAdmins.
    
    b. Abra **Usuarios y equipos de Active Directory**, expanda el dominio, haga clic en el contenedor **Usuarios**, haga clic con el botón secundario en CSAdministrator y seleccione **Propiedades**.
    
    c. En **Propiedades de CSAdministrator**, haga clic en la pestaña **Miembros**.
    
    d. En la pestaña **Miembros**, haga clic en **Agregar**. En **Seleccionar usuarios, contactos, equipos, cuentas de servicio o grupos**, busque **Escribir los nombres de objeto para seleccionar**. Escriba el nombre o los nombres de usuario, o bien el nombre o los nombres de grupo que desee agregar al grupo CSAdministrators. Haga clic en **Aceptar**.
    
    e. En la pestaña **Miembros**, confirme que estén los usuarios o los grupos que haya seleccionado. Haga clic en **Aceptar**.
    
    > [!CAUTION]
    > El Skype para Business Server Control Panel es una herramienta de control de acceso basado en funciones. Pertenencia al grupo CsAdministrator da a un usuario que está utilizando el Skype para control total del Panel de Control de servidor de negocios para todas las funciones de configuración disponibles. Hay otros roles disponibles diseñados para funciones específicas. Para obtener detalles sobre las funciones disponibles, vea [los requisitos ambientales para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md). Tenga en cuenta que los usuarios no deben estar habilitados para Skype para Business Server con el fin de hacerse miembros de los grupos de administración. 
  
    > [!CAUTION]
    > Para ayudar a mantener la seguridad y la integridad de control de acceso basado en funciones, agregar usuarios a los grupos que definen qué función realiza el usuario en la gestión de la Skype para la implementación de Business Server. 
  
11. Cierra la sesión y volver a iniciarla Windows para que se actualice el token de seguridad con el nuevo Skype para el grupo de seguridad servidores empresariales y vuelva a abrir al Asistente para implementación.
    
12. Compruebe que haya una marca de verificación verde junto a **Preparar Active Director** para comprobar que la acción se realizó correctamente, tal como se muestra en la figura.
    
     ![Preparación de Active Directory completada.](../../media/1fbb655a-25c3-4652-96f9-af0427def17d.png)
  

