Building your Crud on Portal

1) Go up the portal: docker run -it -p 8080:8080 liferay/dxp:7.3.10-ga1
2) npm run-script build (create a folder "dist" with the file .jar)
3) Run the command: docker cp [path file.jar].jar [container name]:/opt/liferay/deploy
** d ps to see the container's name**
4) Login on Portal;
5)Clean Cache
6) Go to Edit >> search your project name >> drag and drop

$ Make sure that before doing these steps:
    -create a file babel.config.js put the following code inside(
        
        module.exports = {
    presets: [
      ['@babel/preset-env', { targets: { node: 'current' } }],
      ['@babel/preset-react', { targets: { node: 'current' } }]
    ]
  }
    )
    - Put the "liferay-npm-bundler --create.jar" inside the 
    package.json >> script >> build

    -Put the following fragment in .babelrc(

        {
	"presets": [
			"@babel/preset-env",
			"@babel/preset-react"
		],
		"plugins": [
			"@babel/plugin-transform-react-jsx"
		]
	}

    )   