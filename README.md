# Instalando o TypeScript
npm i -D typescript

# Após instalar o typescript vamos ter acesso ao comando tsc.
# Para inicializar um projeto TypeScript vamos executar o comando npx tsc --init

# Vamos configurar o typescript para o desenvolvimento, editando as configurações em tsconfig.json

# Configurações recomendadas

    "target": "es2016", 
    "module": "commonjs", 
    "rootDir": "./src/", 
    "moduleResolution": "node",
    "outDir": "./dist/", /* pasta para gerar o código transpilado o código em javascript

# Acrescentar no final do arquivo tsconfig.json
  "exclude": [
    "__tests__",
    "jest-config.ts"
  ],
  "ts-node": {
    "transpileOnly": true
  }

# Para transpilar os arquivos .ts você precisa usar
npx tsc

# Criei no package.json a entrada para transpilar
npm run transpile

# Depois de transpilar é possível executar os códigos com 
npm start

# Para não ficar executando o npx na frente é possível instalar o TypeScript globalmente

# Para rodar o código é preciso compilar e depois rodar
    npx tsc
    node ./dist/index.
    
# Instalando a biblioteca de test Jest
    npm i -D jest ts-jest @types/jest

# Configurar o Jest como o jest --init
    npx jest --init
    
# Responda Y para criar o script de test no package.json
# Responda Y para usar o TypeScript no arquivo de configuração
# Escolha node para programação node ou jsdom para browser (use o node)
# Diga sim para criar o relatório de cobertura de código
# Escolha o V8 como instrumento de cobertura de código
# Responda Y para limpar mock calls em cada teste.

# Pronto. Foi criado um jest.config.ts na raiz.

# Edite o arquivo jest.config.ts

# Mude os seguintes campos:

    collectCoverageFrom: ["<rootDir>/src/**/*."],

    coverageReporters: [
        "text",
        "lcov"
    ],

    preset: "ts-jest",

    testMatch: ["**/__tests__/**/*.ts"],