# Component communication via data binding

## Bookmark
https://www.udemy.com/the-complete-guide-to-angular-2/learn/v4/t/lecture/6656114?start=0

## Run
npm start
localhost:4200

## Resources
https://blog.angular-university.io/angular-ng-content/

## Child notifies the parent of the event
    cockpit.component.html
        <button
            (click)="onAddServer(serverNameInput)">Add Server</button>
    cockpit.component.ts
        @Output() serverCreated = new EventEmitter<{serverName: string, serverContent: string}>();

    app.component.html
        <app-cockpit
            (serverCreated)="onServerAdded($event)"
    app.component.ts
        onServerAdded(serverData: {serverName: string, serverContent: string}) {
            this.serverElements.push({
            type: 'server',
            name: serverData.serverName,
            content: serverData.serverContent

           -- cockpit--                                                 -- app -- 
    onAddServer(nameInput: HTMLInputElement) vs  onServerAdded(serverData: {serverName: string, serverContent: string}) 

## Local reference
    <input type='text
        #srvNameInput
    >

