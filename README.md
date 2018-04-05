# Fetch Progress

    Progress of response for fetch API

## Install

`npm i fetch-progress`

## Usage

import `fetchProgress` method to your project

`import fetchProgress from 'fetch-progress`

Now use `fetchProgress` method on your fetch calls, try to put this before using response. You can

```
fetch(this.props.src)
    .then(
      fetchProgress({
        // implement onProgress method
        onProgress(progress) {
          console.log({ progress });
        },
      })
    )
```

# Example

```
import fetchProgress from '../index';

const self = this;
    fetch(this.props.src)
      .then(
        fetchProgress({
          onProgress(progress) {
            self.setState({ progress });
          },
        })
      )
      .then(r => r.blob())
      .then(src => {
        this.src = URL.createObjectURL(src);
        this.setState({
          loaded: true,
        });
      });
```

# Demo

Clone this repo and run `npm i` and `npm run dev` which will start a server or you can see `examples/` folder in this repo.
