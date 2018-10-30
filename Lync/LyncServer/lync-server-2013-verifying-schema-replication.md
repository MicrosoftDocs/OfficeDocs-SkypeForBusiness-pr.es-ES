---
title: 'Lync Server 2013: Comprobar la replicación de esquemas'
TOCTitle: Comprobar la replicación de esquemas
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48276334
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comprobar la replicación de esquemas de Active Directory en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-29_

Antes de realizar la preparación del bosque, compruebe manualmente que la división del esquema se haya replicado.

## Para comprobar manualmente la replicación del esquema

1.  Inicie sesión en un controlador de dominio como miembro del grupo Administradores de organización.

2.  Abra el Editor ADSI. Para ello, haga clic en **Inicio** , **Herramientas administrativas** y, a continuación, haga clic en **Editor ADSI** .
    
    > [!TIP]  
    > También puede ejecutar <strong>adsiedit.msc</strong> en la línea de comandos.
    


3.  En el árbol de Microsoft Management Console (MMC), haga clic en **Editor ADSI** si aún no está seleccionado.

4.  En el menú **Acción** , haga clic en **Conectar con** .

5.  En el cuadro de diálogo **Configuración de conexión** , en **Seleccione un contexto de nomenclatura conocido** , seleccione **Esquema** y, a continuación, haga clic en **Aceptar** .

6.  En el contenedor de esquema, busque CN=ms-RTC-SIP-SchemaVersion. Si este objeto existe y el valor del atributo **rangeUpper** es 1150 y el valor del atributo **rangeLower** es 3, el esquema se ha actualizado y replicado correctamente. Si este objeto no existe o los valores de los atributos **rangeUpper** y **rangeLower** son distintos de lo que se ha especificado, el esquema no se ha modificado o no se ha replicado.

## Vea también

#### Tareas

[Ejecutar la preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-running-schema-preparation.md)  

#### Conceptos

[Preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

