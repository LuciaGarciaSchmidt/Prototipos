# Ant Design - referencia local

Esta referencia mantiene la configuración prevista para los prototipos y la futura implementación React.

## Paquetes

Usar la versión estable más reciente disponible al instalar:

```bash
npm install antd@latest @ant-design/icons@latest
```

Después de instalar, conservar `package-lock.json` para fijar las versiones exactas y poder continuar sin internet.

## Dependencias esperadas

```json
{
  "dependencies": {
    "antd": "latest",
    "@ant-design/icons": "latest"
  }
}
```

La versión exacta quedará registrada automáticamente en `package-lock.json` después de ejecutar la instalación.

## Imports de iconos

```jsx
import {
  AppstoreOutlined,
  AuditOutlined,
  CheckCircleOutlined,
  CloseCircleOutlined,
  DeleteOutlined,
  DollarOutlined,
  DownloadOutlined,
  EditOutlined,
  EyeOutlined,
  FileSearchOutlined,
  FilterOutlined,
  HomeOutlined,
  PrinterOutlined,
  SearchOutlined,
  SettingOutlined,
  UserOutlined,
} from '@ant-design/icons';
```

## Iconos sugeridos para Admin de CAS

| Uso | Icono |
| --- | --- |
| Inicio | `HomeOutlined` |
| Configuracion | `SettingOutlined` |
| Usuario | `UserOutlined` |
| Filtrar | `FilterOutlined` |
| Buscar | `SearchOutlined` |
| Revisar | `FileSearchOutlined` |
| Autorizar | `CheckCircleOutlined` |
| Rechazar | `CloseCircleOutlined` |
| Emitir | `DollarOutlined` |
| Anular | `DeleteOutlined` |
| Descargar | `DownloadOutlined` |
| Imprimir | `PrinterOutlined` |
| Editar | `EditOutlined` |
| Ver comprobantes | `AuditOutlined` |

## Configuracion visual inicial

Los componentes Ant Design deben mapearse a los tokens de `design-system.css`:

- Verde institucional: `#4D5A2F`
- Verde activo: `#909B39`
- Verde grass: `#80BC00`
- Verde claro: `#369040`
- Bone: `#E5E0DE`
- Error: `#FF4D4F`
- Fondo de fila seleccionada: `#F4F5EB`
- Fuente: stack por defecto de Ant Design
- Ancho de referencia: `1366px`
- Alto de referencia: `1101px`

Ejemplo de `ConfigProvider`:

```jsx
import { ConfigProvider } from 'antd';

const theme = {
  token: {
    colorPrimary: '#909B39',
    colorSuccess: '#369040',
    colorError: '#FF4D4F',
    colorText: '#000000',
    colorBorder: '#A6A6A6',
    borderRadius: 4,
    fontFamily: '-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif',
  },
};

export function App() {
  return (
    <ConfigProvider theme={theme}>
      {/* Aplicacion */}
    </ConfigProvider>
  );
}
```

## Trabajo sin internet

1. Ejecutar una vez con internet:

```bash
npm install antd@latest @ant-design/icons@latest
```

2. Conservar estos elementos en el proyecto:

- `package.json`
- `package-lock.json`
- `node_modules/`

3. Para instalar exactamente lo guardado en el lockfile:

```bash
npm ci --offline
```

Si el cache local de npm no contiene los paquetes, `npm ci --offline` requerira que la instalacion inicial se haya realizado previamente con internet.

## Nota

En este workspace no hay actualmente un proyecto React ni Node/npm disponible. Los prototipos HTML pueden seguir usando este archivo como contrato visual hasta migrarlos a componentes React de Ant Design.
