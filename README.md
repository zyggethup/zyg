function callback(fnName,...args){
  const {options} = this;
  options && options[fnName]
  ? options[fnName](this,...args)
  :(options
      &&options.actions[fnName]
      &&options.actions[fnName](this,...args))||
  this.$emit('callback',fnName,...args);
}
