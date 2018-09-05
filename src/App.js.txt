import React, { Component } from 'react';

class App extends Component {
  constructor(){
    super();
    this.state = {
      robo:'', hash:'',
    }
  }
  aksi(){
    var hash = this.refs.img.value;
    var ubah = Math.floor(Math.random() * 10) + 1;
    var link = `https://robohash.org/${hash}?set=set${ubah}`;

    this.setState({robo:link})
  }

  render() {
    
    return (
      <div className="container" style={{background: 'lightblue'}}>
        <div className="form-group col-xs-12 col-sm-6 col-md-4 col-lg-3" style={{padding: '30px'}}>
          <input className="form-control" ref='img' type="text" placeholder="Ketik nama Anda..."/>
          <button onClick={()=>{this.aksi()}} className="btn btn-success btn-md m-3">Buat Profile Picture!</button>
            <div>
            <div className="col-xs-12 col-md-12 col-xl-12 col-sm-12"><img className="rounded-circle img-fluid" style={{background: 'white'}} src={this.state.robo} hash={this.img}/></div>
            </div>
        </div>
      </div>
	)
  }
}

export default App;
