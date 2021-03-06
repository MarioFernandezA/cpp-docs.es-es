---
title: __vmx_vmwrite
ms.date: 11/04/2016
f1_keywords:
- __vmx_vmwrite
helpviewer_keywords:
- __vmx_vmwrite intrinsic
- VMWRITE instruction
ms.assetid: 88139792-fd3f-4210-97ca-9d84f43a0252
ms.openlocfilehash: e368a1f6be51d37cdfe7ef352fca69e987fed62d
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328570"
---
# <a name="vmxvmwrite"></a>__vmx_vmwrite

**Específicos de Microsoft**

Escribe el valor especificado en el campo especificado en la estructura de control de máquina virtual (VMCS) actual.

## <a name="syntax"></a>Sintaxis

```
unsigned char __vmx_vmwrite(
   size_t Field,
   size_t FieldValue
);
```

#### <a name="parameters"></a>Parámetros

|Parámetro|Descripción|
|---------------|-----------------|
|*Campo*|[in] El campo VMCS a escribir.|
|*FieldValue*|[in] El valor para escribir en el campo VMCS.|

## <a name="return-value"></a>Valor devuelto

0 de la operación se realizó correctamente.

1 error en la operación con el estado extendido disponible en el `VM-instruction error field` de la VMCS actual.

2 no se pudo la operación sin estado disponible.

## <a name="remarks"></a>Comentarios

La función `__vmx_vmwrite` equivale a la instrucción máquina `VMWRITE` . El valor de la `Field` parámetro es un índice de campo codificado que se describe en la documentación de Intel. Para obtener más información, busque el documento, "Intel Virtualization Technical especificación para la arquitectura IA-32 Intel," documento C97063-002, número en el [Intel Corporation](https://software.intel.com/articles/intel-sdm) de sitio y, a continuación, consulte el apéndice C de la que documento.

## <a name="requirements"></a>Requisitos

|Función intrínseca|Arquitectura|
|---------------|------------------|
|`__vmx_vmwrite`|x64|

**Archivo de encabezado** \<intrin.h >

**FIN de Específicos de Microsoft**

## <a name="see-also"></a>Vea también

[Intrínsecos del controlador](../intrinsics/compiler-intrinsics.md)<br/>
[__vmx_vmread](../intrinsics/vmx-vmread.md)